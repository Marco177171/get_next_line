# 42 get_next_line

Welcome to the get_next_line Recreation project! This project is focused on reimplementing the `get_next_line` function in C, which reads a single line from a file descriptor.

## Project Overview

The main objective of this project is to create a function that reads a line from a file descriptor and handles multiple file descriptors without losing the reading thread.

### Key Features

- **Reading Lines**: Implementation of a function to read a line from a file descriptor, handling newline terminators.
- **Handling Multiple File Descriptors**: Capability to manage multiple file descriptors concurrently without interference.

## How get_next_line Works

The `get_next_line` function reads a line (terminated by a newline character) from a file descriptor and returns that line without the newline character at the end.

## Usage Example

To use the `get_next_line` function in your C program:

1. Include the header file containing the `get_next_line` function.
2. Call the `get_next_line` function by passing the file descriptor and a pointer to a char pointer.
3. Manage the return value and handle errors or end-of-file situations.

### Example Code

```c
#include "get_next_line.h"

int main(int argc, char **argv) {
    int fd;
    char *line;
    int ret;

    if (argc != 2) {
        write(1, 'error\n', 6);
        return (1);
    }
    fd = fopen(argv[1], O_RDONLY)

    while ((ret = get_next_line(fd, &line)) > 0) {
        printf("Line read: %s\n", line);
        free(line);
    }

    if (ret == 0) {
        printf("End of file reached.\n");
    }
    else if (ret == -1) {
        printf("Error occurred while reading.\n");
    }

    close(fd);
    return (0);
}
```

### Contacts

- Email: msebastiani93@gmail.com
- GitHub: https://github.com/Marco177171

Thank you for exploring the get_next_line Recreation project! Your interest and contributions are valuable.

Best regards,
Marco Sebastiani
