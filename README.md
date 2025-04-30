# WET (Event Tracing for Windows)

WET is a tracing facility that allows a user to log events to a file (JSON, XML, CSV)


<details>

<summary>Install required tools on Windows</summary>

### For Windows 11

```powershell
```
</details>

<details>

<summary>Install required python libs</summary>

### pip install
```powershell
pip install -r requirements.txt
python3 setup.py install
```

### conda install
```powershell
conda config --add channels conda-forge
conda install --file requirements_conda.txt
python3 setup.py install
```

</details>



## Common Windows Kernel Event Types

| **Event Type**             | **Description**                                                          | **Subsystem / Use Case**               |
|----------------------------|---------------------------------------------------------------------------|----------------------------------------|
| `IRP_MJ_CREATE`            | Request to create or open a file/device                                  | I/O Manager / File System              |
| `IRP_MJ_READ`              | Read from a file or device                                               | I/O Manager                            |
| `IRP_MJ_WRITE`             | Write to a file or device                                                | I/O Manager                            |
| `IRP_MJ_CLOSE`             | Close handle to a file or device                                         | I/O Manager                            |
| `IRP_MJ_DEVICE_CONTROL`    | Device-specific control operation (IOCTL)                                | I/O Manager                            |
| `IRP_MJ_DIRECTORY_CONTROL` | Query or change a directory                                              | File System                            |
| `IRP_MJ_QUERY_INFORMATION` | Query file/device metadata                                               | File System                            |
| `IRP_MJ_SET_INFORMATION`   | Set file/device metadata                                                 | File System                            |
| `IRP_MJ_CREATE_NAMED_PIPE` | Create a named pipe                                                      | File System / IPC                      |
| `PsCreateProcessNotify`    | Process creation notification                                            | Kernel process manager                 |
| `PsCreateThreadNotify`     | Thread creation notification                                             | Kernel process manager                 |
| `PsSetLoadImageNotify`     | Image (executable/DLL) load notification                                | Kernel / Security                      |
| `CmRegisterCallback`       | Registry callback for key creation/modification/deletion                 | Configuration Manager / Registry       |
| `REG_NT_SET_VALUE_KEY`     | Set a registry key value                                                 | Registry                               |
| `REG_NT_CREATE_KEY`        | Create a registry key                                                    | Registry                               |
| `REG_NT_DELETE_KEY`        | Delete a registry key                                                    | Registry                               |
| `FLT_POSTOP_CALLBACK`      | Post-operation callback in a minifilter driver (e.g., file read/write)   | File System Filter Driver              |
| `FLT_PREOP_CALLBACK`       | Pre-operation callback in a minifilter driver                            | File System Filter Driver              |
| `ETW_EVENT_PROCESS_CREATE` | Process creation event in Event Tracing for Windows                      | ETW / Kernel Provider                  |
| `ETW_EVENT_PROCESS_EXIT`   | Process exit event in ETW                                                | ETW / Kernel Provider                  |
| `ETW_EVENT_IMAGE_LOAD`     | Image load event (DLL, EXE) in ETW                                       | ETW / Kernel Provider                  |
| `ETW_EVENT_THREAD_CREATE`  | Thread creation event in ETW                                             | ETW / Kernel Provider                  |
| `ETW_EVENT_DISK_IO_READ`   | Disk read event captured via ETW                                         | ETW / Disk I/O                         |
| `ETW_EVENT_NETWORK_TCP`    | TCP packet transmission event in ETW                                     | ETW / Network stack                    |
| `KeBugCheck`               | Kernel-mode crash (bug check/BSOD)                                       | Kernel mode                            |
