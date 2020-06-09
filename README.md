# loadup

header only library for NtLoadDriver/NtUnloadDriver. 

# examples

loading driver from buffer.

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