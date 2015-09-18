# Telegraf plugin: CPU

The CPU plugin collects standard CPU metrics as defined in `man proc`. All
architectures do not support all of these metrics.

```
cpu  3357 0 4313 1362393
    The amount of time, measured in units of USER_HZ (1/100ths of a second on
    most architectures, use sysconf(_SC_CLK_TCK) to obtain the right value),
    that the system spent in various states:

    user   (1) Time spent in user mode.

    nice   (2) Time spent in user mode with low priority (nice).

    system (3) Time spent in system mode.

    idle   (4) Time spent in the idle task.  This value should be USER_HZ times
    the second entry in the /proc/uptime pseudo-file.

    iowait (since Linux 2.5.41)
           (5) Time waiting for I/O to complete.

    irq (since Linux 2.6.0-test4)
           (6) Time servicing interrupts.

    softirq (since Linux 2.6.0-test4)
           (7) Time servicing softirqs.

    steal (since Linux 2.6.11)
           (8) Stolen time, which is the time spent in other operating systems
           when running in a virtualized environment

    guest (since Linux 2.6.24)
           (9) Time spent running a virtual CPU for guest operating systems
           under the control of the Linux kernel.

    guest_nice (since Linux 2.6.33)
           (10) Time spent running a niced guest (virtual CPU for guest operating systems under the control of the Linux kernel).
```

# Measurements:
### CPU Time measurements:

Meta:
- units: CPU Time
- tags: `cpu=<cpuN> or <cpu-total>`

Measurement names:
- cpu_user
- cpu_system
- cpu_idle
- cpu_nice
- cpu_iowait
- cpu_irq
- cpu_softirq
- cpu_steal
- cpu_guest
- cpu_guest_nice

### CPU Usage Percent Measurements:

Meta:
- units: percent (out of 100)
- tags: `cpu=<cpuN> or <cpu-total>`

Measurement names:
- cpu_usage_user
- cpu_usage_system
- cpu_usage_idle
- cpu_usage_nice
- cpu_usage_iowait
- cpu_usage_irq
- cpu_usage_softirq
- cpu_usage_steal
- cpu_usage_guest
- cpu_usage_guest_nice