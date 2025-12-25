# Weather Forecast

A REST API that acts as a proxy to an external weather provider (like OpenWeatherMap or WeatherAPI), adding a caching layer to optimize costs and latency. The core challenge is implementing effective caching strategies.

## Functional Requirements (FR):

-   **FR01 (Get Weather)**: The system must provide an endpoint that accepts a location (e.g., city name or latitude/longitude) and returns current weather data.

-   **FR02 (External Integration)**: The application must fetch real data from a third-party weather API.

-   **FR03 (Cache Hit)**: If the same location is requested within a configurable time window (e.g., 15 minutes), the system must return the cached response instead of calling the external API.

-   **FR04 (Cache Miss)**: If the data is not in cache or has expired, the system must fetch fresh data from the external API, store it in the cache, and then return it.

## Non-Functional Requirements (NFR):

-   **NFR01 (Configuration)**: API keys for the external provider must be managed via environment variables, never hardcoded.

-   **NFR02 (Caching Mechanism)**: Use an in-memory store (like Redis) or a robust in-memory library. The caching logic must be explicitly demonstrated.

-   **NFR03 (Rate Limiting)**: (Optional but recommended) Implement basic rate limiting to prevent abuse of the proxy.

-   **NFR04 (Resilience)**: Handle errors gracefully if the external API is down (e.g., return the last known cached data if available, or a friendly error).

-   **NFR05 (Failover Strategy)**: (Optional) Support configuration for multiple external weather API providers (from 1 to N). If the primary provider fails, the system should automatically attempt to fetch data from the next available provider in the list.

## Improvements

-   **FR05 (Alerts)**: Allow users to register a location and an email address.
-   **FR06 (Notification)**: Send an automated email when specific weather conditions are met (e.g., "It will rain tomorrow in London"). You may use a mock SMTP server (like Mailhog) or a real provider.