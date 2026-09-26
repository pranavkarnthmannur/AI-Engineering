# Monitoring and Tracing a Generative AI Agent

Microsoft Learn GenAIOps exercise demonstrating runtime monitoring and distributed tracing for a generative AI application.

## What I Built

I tested three versions of a Trail Guide Agent system prompt using the same five test questions and the same GPT-5-mini deployment.

The application uses:

- Azure OpenAI / Microsoft Foundry
- Application Insights
- Log Analytics
- OpenTelemetry
- Python
- GPT-5-mini

OpenTelemetry captures traces for each model interaction, including latency and token usage.

## Experiment

Each prompt version was tested against five identical user prompts.

| Version | Total Tokens | Total Runtime | Average Latency |
|---|---:|---:|---:|
| V1 | 5,427 | 44.7 sec | 8.9 sec |
| V2 | 11,125 | 72.3 sec | 14.5 sec |
| V3 | 11,670 | 100.9 sec | 20.2 sec |

The experiment showed that changes to the system prompt can significantly affect token consumption and response latency.

In this run, V1 used the fewest tokens and had the lowest latency. V2 and V3 generated substantially more completion tokens, while V3 had the highest overall runtime.

## Distributed Tracing

The monitoring implementation creates:

- A parent span for each prompt version
- A child span for each test prompt
- An automatically instrumented span for each GPT model call

Example:

trail_guide_v1
  -> v1_day-hike-gear
      -> chat gpt-5-mini

Application Insights and Log Analytics successfully received the telemetry.

The trace query returned 35 spans across the experiment.

## Run

Install dependencies:

python -m pip install -r requirements.txt

Create a `.env` file using `.env.example` as a template.

Run the monitoring experiment:

python src/tests/run_monitoring.py

Check the distributed traces:

python src/tests/check_traces.py

## Key Learning

Monitoring generative AI applications is useful for understanding the operational impact of prompt changes. A prompt that produces a better or more detailed response may also increase token usage, latency and therefore operating cost.

Source exercise: Microsoft Learn - GenAIOps Monitoring and Tracing.
