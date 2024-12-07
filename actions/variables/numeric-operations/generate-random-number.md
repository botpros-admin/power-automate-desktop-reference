# Generate Random Number

## Description
Generate a random number or a list of random numbers that fall between a minimum and maximum value.

## Syntax
```
Variables.GenerateRandomNumber.RandomNumber MinimumValue: 0 MaximumValue: 100 RandomNumber=> RandomNumber
```

## Input Parameters

| Parameter | Required | Accepts | Default Value | Description |
|-----------|----------|---------|---------------|-------------|
| Minimum value | No | Numeric value | 0 | Lower boundary |
| Maximum value | No | Numeric value | 100 | Upper boundary |
| Generate multiple numbers | No | Boolean value | False | Generate single or multiple numbers |
| How many numbers | No | Numeric value | 10 | Count of numbers to generate |
| Allow duplicates | No | Boolean value | False | Allow repeat numbers in list |

## Output Variables

| Variable | Type | Description |
|----------|------|-------------|
| RandomNumber | Numeric value | Single random number |
| RandomNumbers | List of Numeric values | List of random numbers |

## Exceptions

| Exception | Description |
|-----------|-------------|
| Failed to generate random number | Error in random number generation |