*Marcel Plakolb 3AHIF*
# System Calls
## Fork
Creates new process by duplicating the calling process the new process is called child process.

No arguments

## Stat
Returns information about a file from the path.

Function argument:
const char * restrict path -> path to the file
struct stat * restrict buf -> information about the file

### Arguments
#### char* pathname
* The file from where you want the information.

#### struct stat* statbuf
* Return buffer

## Kill
Can be used to send a signal to any process

Function argument:
int sig -> type of signal
pid_t pid -> who will receive the signal

### Arguments
#### pid_t pid
* Is the process ID, if it is 0 sig is sent to every process in the process group.

#### int sig
* The signal to send to a process if 0 can be used to check if a process exists.

## mmap
Creates a new mapping in virutal address space of the process.
### Arguments

#### void* addr
* The starting address of the mapping.
#### size_t length
* Specifies the length of the new mapping starting from addr.
#### int prot 
* Specifies the protections
#### int flags
* Specifies the type of the mapped object, mapping options
#### int fd
* File descriptor
#### off_t offset
* starting point

## chmod
Changes a file mode bits.

### Arguments
#### const char* path
* Path that points to the file.
#### mode_t mode
* What has to be changed.

## waitpid
Provides a general interface for processes that need to wait for child processes.

### Arguments
#### pid_t pid
* The process id for which to wait.
#### int * stat_loc
* Location where to store a status value.
#### int options
* Contains the bitwise

# Fail
## fork
* When there is now memory for the new process.
## exec 
* The argument list exceeds the system limit.
## unlink
* Permission denied.
## read
* When a directory is tried to read.
## mount
* A path that is a file not a directory.
## chmod
* Mode is not a valid file mode.
## kill
* A entered process id is not a process or process group

# Traps
* Is a exception in a user process. Caused by division by zero. Invokes a kernel routine (system call), those run with higer priority.