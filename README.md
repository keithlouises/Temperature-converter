
    # Convert input to Celsius first
    if from_unit == 'C':
        celsius = value
    elif from_unit == 'F':
        celsius = (value - 32) * 5/9
    elif from_unit == 'K':
        celsius = value - 273.15
    elif from_unit == 'R':
        celsius = (value - 491.67) * 5/9
    else:
        return "Invalid from_unit"

    # Convert from Celsius to target unit
    if to_unit == 'C':
        return celsius
    elif to_unit == 'F':
        return (celsius * 9/5) + 32
    elif to_unit == 'K':
        return celsius + 273.15
    elif to_unit == 'R':
        return (celsius + 273.15) * 9/5
    else:
        return "Invalid to_unit"

# User input
value = float(input("Enter temperature value: "))
from_unit = input("Enter current unit (C, F, K, R): ").strip().upper()
to_unit = input("Enter unit to convert to (C, F, K, R): ").strip().upper()

# Conversion and output
converted = convert_temperature(value, from_unit, to_unit)
if isinstance(converted, str):
    print(converted)
else:
    print(f"Temperature in {to_unit}: {converted:.2f}")
