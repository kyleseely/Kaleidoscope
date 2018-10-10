# Kaleidoscope-HostPowerManagement

[![Build Status][travis:image]][travis:status]

 [travis:image]: https://travis-ci.org/keyboardio/Kaleidoscope-HostPowerManagement.svg?branch=master
 [travis:status]: https://travis-ci.org/keyboardio/Kaleidoscope-HostPowerManagement

Support performing custom actions whenever the host suspends, resumes, or is
sleeping.

## Using the plugin

To use the plugin, one needs to include the header, and activate it. No further
configuration is necessary, unless one wants to perform custom actions.

```c++
#include <Kaleidoscope.h>
#include <Kaleidoscope-HostPowerManagement.h>

KALEIDOSCOPE_INIT_PLUGINS(HostPowerManagement);

void setup () {
  Kaleidoscope.setup ();
}
```

## Plugin methods

The plugin provides the `HostPowerManagement` object, with no public methods.

## Overrideable methods

### `hostPowerManagementEventHandler(event)`

> The `hostPowerManagementEventHandler` method is the brain of the plugin: this function
> tells it what action to perform in response to the various events.
>
> Currently supported events are: `kaleidoscope::HostPowerManagement::Suspend` is fired
> once when the host suspends; `kaleidoscope::HostPowerManagement::Sleep` is fired every
> cycle while the host is suspended; `kaleidoscope::HostPowerManagement::Resume` is
> fired once when the host wakes up.
>
> The default implementation is empty.

## Further reading

Starting from the [example][plugin:example] is the recommended way of getting
started with the plugin.

 [plugin:example]: https://github.com/keyboardio/Kaleidoscope-HostPowerManagement/blob/master/examples/HostPowerManagement/HostPowerManagement.ino
