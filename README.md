# loadup

Header only library for NtLoadDriver annd NtUnloadDriver. Registry entries and temp files that may be created are deleted when `driver::unload(...)` is called.

# examples

loading driver from buffer. `warning` please ensure ALL handles are closed to the driver before unloading the driver! `CloseHandle`!

```cpp
std::vector<std::uint8_t> drv_buffer(...);
const auto[result, reg_key] = driver::load(drv_buffer.data(), drv_buffer.size());
```

load driver from path on disk.

```cpp
const bool result = driver::load("image.sys", "image_key");
```

unloading driver.

```cpp
const bool result = driver::unload("image_key");
```