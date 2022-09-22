# .NET and the OpenTelemetry Collector Example

This repository shows an example of attaching a .NET web application to the OpenTelemetry Collector. Additionally, the collector is then configured to forward spans to both a local Jaeger instance as well the Honeycomb SaaS platform.

## Running

First you'll need your Honeycomb API key from the Honeycomb portal.

Note: This example will only work if you're using a team with the Environments & Services feature enabled.

```bash
export HONEYCOMB_API_KEY=<your key>
```

From the root of the repository

```bash
docker-compose up -d
dotnet run --project src/
```

## Usage

You can access the website on [http://localhost:7219](http://localhost:7219). Click around to generate some tracing data.

You can then access Jaeger on [http://localhost:16686](http://localhost:16686/). Select the service `dotnet-otel-collector` and "Find Traces".
