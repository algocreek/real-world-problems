# Rate Limiter Implementation

## Background

Rate limiters are commonly used as a throttling solution to protect systems from traffic surges. They're typically applied at the API layer to prevent overwhelming downstream resources.

**Real-world use cases:**
- Protecting APIs from abuse or DDoS attacks
- Enforcing usage quotas for different customer tiers
- Preventing resource exhaustion in microservices
- Managing third-party API consumption costs

## Problem Statement

Implement two rate limiting algorithms commonly used in production systems:

### 1. Sliding Window Rate Limiter
Tracks requests within a rolling time window to provide smooth rate limiting without the burst issues of fixed windows.

**Requirements:**
- Allow N requests per time window
- Window slides continuously (not fixed intervals)
- Reject requests exceeding the limit
- Memory efficient for high-traffic scenarios

### 2. Token Bucket Rate Limiter
Uses a bucket that fills with tokens at a steady rate, allowing burst traffic up to bucket capacity.

**Requirements:**
- Bucket refills at a constant rate
- Support burst traffic up to bucket size
- Tokens consumed per request
- Handle concurrent access safely

## Expected Implementation

For each algorithm, provide:
- Core rate limiting logic
- Thread-safe implementation
- Configuration options (rate, window size, bucket capacity)
- Clear API for checking and consuming rate limits
- Example usage demonstrating typical scenarios

## Success Criteria

- Correctly enforces rate limits under load
- Handles edge cases (concurrent requests, time boundaries)


