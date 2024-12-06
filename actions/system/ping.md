# Ping

## Description
Sends a message to determine whether a remote computer is accessible over the network.

## Syntax
```
System.Ping HostName: `[host name]` Timeout: 5000 PingResult=> PingResult RoundTripTime=> RoundTripTime
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Host name | Yes | Text value | - | The name of the remote computer or an IP address |
| Timeout | No | Numeric value | 5000 | The maximum number of milliseconds to wait for the Ping reply message |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| PingResult | Text value | The status of the ping message (success or failure) |
| RoundTripTime | Numeric value | The number of milliseconds taken for the Ping to complete |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Can't complete ping action | Indicates a problem completing the ping action |