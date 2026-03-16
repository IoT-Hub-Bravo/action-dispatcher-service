# IoT Hub Action Dispatcher Service

Service for executing external actions such as webhook delivery with retries and delivery tracking.

## Purpose

The Action Dispatcher Service executes side effects triggered by alerts or rule outcomes.

## Responsibilities

- consume action execution requests
- execute configured outbound actions
- perform webhook delivery
- apply retry and backoff policies
- track delivery attempts and outcomes
- publish delivery success or failure events

## Owned data

- delivery attempts
- delivery status
- response metadata
- execution-related technical state

## Integrations

### Inbound
- action execution requests
- internal action-triggering flows

### Outbound
- external systems such as webhook targets
- action delivery audit

## Technology

- Python
- Kafka
- Docker
