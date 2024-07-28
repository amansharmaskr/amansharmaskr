import logging

# Basic configuration for logging with a file handler
logging.basicConfig(
    level=logging.DEBUG,
    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s',
    datefmt='%Y-%m-%d %H:%M:%S',
    handlers=[
        logging.StreamHandler(),               # Console handler
        logging.FileHandler('calculator.log')  # File handler
    ]
)

# Create a logger
logger = logging.getLogger('calculator')

def add(a, b):
    result = a + b
    logger.debug(f'Addition: a={a}, b={b}, result={result}')
    return result

def subtract(a, b):
    result = a - b
    logger.debug(f'Subtraction: a={a}, b={b}, result={result}')
    return result

def multiply(a, b):
    result = a * b
    logger.debug(f'Multiplication: a={a}, b={b}, result={result}')
    return result

def divide(a, b):
    try:
        result = a / b
        logger.debug(f'Division: a={a}, b={b}, result={result}')
        return result
    except ZeroDivisionError:
        logger.error(f'Division error: Cannot divide {a} by zero.')
        return None

# Example usage
if __name__ == "__main__":
    add(10, 5)
    subtract(10, 5)
    multiply(10, 5)
    divide(10, 0)
    divide(10, 2)


2024-07-28 12:00:00 - calculator - DEBUG - Addition: a=10, b=5, result=15
2024-07-28 12:00:00 - calculator - DEBUG - Subtraction: a=10, b=5, result=5
2024-07-28 12:00:00 - calculator - DEBUG - Multiplication: a=10, b=5, result=50
2024-07-28 12:00:00 - calculator - ERROR - Division error: Cannot divide 10 by zero.
2024-07-28 12:00:00 - calculator - DEBUG - Division: a=10, b=2, result=5.0
