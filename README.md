import logging

logging.basicConfig(level=logging.DEBUG)
logger = logging.getLogger()

logger.debug('This is a debug message')
logger.info('This is an info message')
logger.warning('This is a warning message')
logger.error('This is an error message')
logger.critical('This is a critical message')

DEBUG:root:This is a debug message
INFO:root:This is an info message
WARNING:root:This is a warning message
ERROR:root:This is an error message
CRITICAL:root:This is a critical message

import logging

log_format = "%(asctime)s - %(levelname)s - %(message)s"
date_format = "%Y-%m-%d %H:%M:%S"

logging.basicConfig(level=logging.DEBUG, format=log_format, datefmt=date_format)
logger = logging.getLogger()

logger.debug('This is a debug message')
logger.info('This is an info message')
logger.warning('This is a warning message')
logger.error('This is an error message')
logger.critical('This is a critical message')


2024-07-28 12:00:00 - DEBUG - This is a debug message
2024-07-28 12:00:00 - INFO - This is an info message
2024-07-28 12:00:00 - WARNING - This is a warning message
2024-07-28 12:00:00 - ERROR - This is an error message
2024-07-28 12:00:00 - CRITICAL - This is a critical message


import logging

log_format = "%(asctime)s - %(levelname)s - %(message)s"
date_format = "%Y-%m-%d %H:%M:%S"

logging.basicConfig(filename='new_file.log', filemode='w', level=logging.DEBUG, format=log_format, datefmt=date_format)
logger = logging.getLogger()

logger.debug('This is a debug message')
logger.info('This is an info message')
logger.warning('This is a warning message')
logger.error('This is an error message')
logger.critical('This is a critical message')


2024-07-28 12:00:00 - DEBUG - This is a debug message
2024-07-28 12:00:00 - INFO - This is an info message
2024-07-28 12:00:00 - WARNING - This is a warning message
2024-07-28 12:00:00 - ERROR - This is an error message
2024-07-28 12:00:00 - CRITICAL - This is a critical message


import logging

# Basic configuration for logging
logging.basicConfig(
    level=logging.DEBUG,
    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s',
    datefmt='%Y-%m-%d %H:%M:%S'
)

# Create a logger for module1
logger1 = logging.getLogger('module1')
logger1.setLevel(logging.DEBUG)  # Set the logging level

def do_something():
    logger1.debug('This is a debug message from module1')
    logger1.info('This is an info message from module1')

# Create a logger for module2
logger2 = logging.getLogger('module2')
logger2.setLevel(logging.INFO)  # Set the logging level

def do_something_else():
    logger2.info('This is an info message from module2')
    logger2.warning('This is a warning message from module2')

# Call functions to generate log messages
do_something()
do_something_else()


2024-07-28 12:00:00 - module1 - DEBUG - This is a debug message from module1
2024-07-28 12:00:00 - module1 - INFO - This is an info message from module1
2024-07-28 12:00:00 - module2 - INFO - This is an info message from module2
2024-07-28 12:00:00 - module2 - WARNING - This is a warning message from module2
