
================================
Available metrics
================================

**This software is pre-production and should not be deployed to production servers.**

For searchable list of metrics `metrics as csv file <metrics.csv>`_ .

The "Enabled" describes if metric is enabled by default and in brackets there is information which 
option in MeasurementRunner is responsible for configuring it.

.. contents:: Table of Contents


Metrics sources
===============

Check out `metrics sources documentation <metrics_sources.rst>`_  to learn how measurement them.

Task's metrics
==============

.. csv-table::
	:header: "Name", "Help", "Enabled", "Unit", "Type", "Source", "Levels/Labels"
	:widths: 5, 5, 5, 5, 5, 5, 5 

	"task_instructions", "Hardware PMU counter for number of instructions.", "no (event_names)", "numeric",  "counter", "perf subsystem with cgroups", ""
	"task_cycles", "Hardware PMU counter for number of cycles.", "no (event_names)", "numeric",  "counter", "perf subsystem with cgroups", ""
	"task_cache_misses", "Hardware counter for cache-misses.", "no (event_names)", "numeric",  "counter", "perf subsystem with cgroups", ""
	"task_cache_references", "Hardware counter for number of cache references.", "no (event_names)", "numeric",  "counter", "perf subsystem with cgroups", ""
	"task_stalled_mem_loads", "TBD: Mem stalled loads.", "no (event_names)", "numeric",  "counter", "perf subsystem with cgroups", ""
	"task_offcore_requests_l3_miss_demand_data_rd", "Increment each cycle of the number of offcore outstanding demand data read requests from SQ that missed L3.", "no (event_names)", "numeric",  "counter", "perf subsystem with cgroups", ""
	"task_offcore_requests_outstanding_l3_miss_demand_data_rd", "Demand data read requests that missed L3.", "no (event_names)", "numeric",  "counter", "perf subsystem with cgroups", ""
	"task_mem_load_retired_local_pmm", "TBD mem_load_retired_local_pmm__rd180", "no (event_names)", "numeric",  "counter", "perf subsystem with cgroups", ""
	"task_mem_load_retired_local_dram", "TBD task__mem_load_retired_local_dram__rd301", "no (event_names)", "numeric",  "counter", "perf subsystem with cgroups", ""
	"task_mem_inst_retired_loads", "TBD mem_load_retired_local_pmm__rd180", "no (event_names)", "numeric",  "counter", "perf subsystem with cgroups", ""
	"task_mem_inst_retired_stores", "TBD", "no (event_names)", "numeric",  "counter", "perf subsystem with cgroups", ""
	"task_dtlb_load_misses", "TBD", "no (event_names)", "numeric",  "counter", "perf subsystem with cgroups", ""
	"task_scaling_factor_avg", "Perf subsystem metric scaling factor, max value of all perf per task metrics.", "yes", "numeric",  "gauge", "perf subsystem with cgroups", ""
	"task_scaling_factor_max", "Perf subsystem metric scaling factor, max value of all perf per task metrics.", "yes", "numeric",  "gauge", "perf subsystem with cgroups", ""
	"task_ips", "Instructions per second.", "no (enable_derived_metrics)", "numeric",  "gauge", "derived", ""
	"task_ipc", "Instructions per cycle.", "no (enable_derived_metrics)", "numeric",  "gauge", "derived", ""
	"task_cache_hit_ratio", "Cache hit ratio, based on cache-misses and cache-references.", "no (enable_derived_metrics)", "numeric",  "gauge", "derived", ""
	"task_cache_misses_per_kilo_instructions", "Cache misses per kilo instructions.", "no (enable_derived_metrics)", "numeric",  "gauge", "derived", ""
	"task_llc_occupancy_bytes", "LLC occupancy from resctrl filesystem based on Intel RDT technology.", "auto (rdt_enabled)", "bytes",  "gauge", "resctrl filesystem", ""
	"task_mem_bandwidth_bytes", "Total memory bandwidth using Memory Bandwidth Monitoring.", "auto (rdt_enabled)", "bytes",  "counter", "resctrl filesystem", ""
	"task_mem_bandwidth_local_bytes", "Total local memory bandwidth using Memory Bandwidth Monitoring.", "auto (rdt_enabled)", "bytes",  "counter", "resctrl filesystem", ""
	"task_mem_bandwidth_remote_bytes", "Total remote memory bandwidth using Memory Bandwidth Monitoring.", "auto (rdt_enabled)", "bytes",  "counter", "resctrl filesystem", ""
	"task_cpu_usage_seconds", "Time taken by task based on cpuacct.usage (total kernel and user space).", "yes", "seconds",  "counter", "cgroup filesystem", ""
	"task_mem_usage_bytes", "Memory usage_in_bytes per tasks returned from cgroup memory subsystem.", "yes", "bytes",  "gauge", "cgroup filesystem", ""
	"task_mem_max_usage_bytes", "Memory max_usage_in_bytes per tasks returned from cgroup memory subsystem.", "yes", "bytes",  "gauge", "cgroup filesystem", ""
	"task_mem_limit_bytes", "Memory limit_in_bytes per tasks returned from cgroup memory subsystem.", "yes", "bytes",  "gauge", "cgroup filesystem", ""
	"task_mem_soft_limit_bytes", "Memory soft_limit_in_bytes per tasks returned from cgroup memory subsystem.", "yes", "bytes",  "gauge", "cgroup filesystem", ""
	"task_mem_numa_pages", "Number of used pages per NUMA node(key: hierarchical_total is used if available or justtotal with warning), from cgroup memory controller from memory.numa_stat file.", "yes", "numeric",  "gauge", "cgroup filesystem", "numa_node"
	"task_mem_page_faults", "Number of page faults for task.", "yes", "numeric",  "counter", "cgroup filesystem", ""
	"task_wss_referenced_bytes", "Task referenced bytes during last measurements cycle based on /proc/smaps Referenced field, with /proc/PIDs/clear_refs set to 1 accordinn wss_reset_interval.Warning: this is intrusive collection, because can influence kernel page reclaim policy and add latency.Refer to https://github.com/brendangregg/wss#wsspl-referenced-page-flag for more details.", "yes", "bytes",  "gauge", "/procs/PIDS/smaps", ""
	"task_requested_cpus", "Tasks resources cpus initial requests.", "yes", "numeric",  "gauge", "orchestrator", ""
	"task_requested_mem_bytes", "Tasks resources memory initial requests.", "yes", "bytes",  "gauge", "orchestrator", ""
	"task_last_seen", "Time the task was last seen.", "yes", "timestamp",  "counter", "internal", ""
	"task_up", "Always returns 1.", "yes", "numeric",  "counter", "internal", ""



Platform's metrics
==================

.. csv-table::
	:header: "Name", "Help", "Enabled", "Unit", "Type", "Source", "Levels/Labels"
	:widths: 5, 5, 5, 5, 5, 5, 5 

	"platform_topology_cores", "Platform information about number of physical cores", "yes", "numeric",  "gauge", "internal", ""
	"platform_topology_cpus", "Platform information about number of logical cpus", "yes", "numeric",  "gauge", "internal", ""
	"platform_topology_sockets", "Platform information about number of sockets", "yes", "numeric",  "gauge", "internal", ""
	"platform_dimm_count", "Number of RAM DIMM (all types memory modules)", "no (gather_hw_mm_topology)", "numeric",  "gauge", "lshw binary output", "dimm_type"
	"platform_dimm_total_size_bytes", "Total RAM size (all types memory modules)", "no (gather_hw_mm_topology)", "bytes",  "gauge", "lshw binary output", "dimm_type"
	"platform_mem_mode_size_bytes", "Size of RAM (Persistent memory) configured in memory mode.", "no (gather_hw_mm_topology)", "numeric",  "gauge", "ipmctl binary output", ""
	"platform_cpu_usage", "Logical CPU usage in 1/USER_HZ (usually 10ms).Calculated using values based on /proc/stat.", "yes", "numeric",  "counter", "/proc filesystem", "cpu"
	"platform_mem_usage_bytes", "Total memory used by platform in bytes based on /proc/meminfo and uses heuristic based on linux free tool (total - free - buffers - cache).", "yes", "bytes",  "gauge", "/proc filesystem", ""
	"platform_mem_numa_free_bytes", "NUMA memory free per NUMA node based on /sys/devices/system/node/* (MemFree:)", "yes", "bytes",  "gauge", "/sys filesystem", "numa_node"
	"platform_mem_numa_used_bytes", "NUMA memory free per NUMA used based on /sys/devices/system/node/* (MemUsed:)", "yes", "bytes",  "gauge", "/sys filesystem", "numa_node"
	"platform_vmstat_numa_pages_migrated", "Virtual Memory stats based on /proc/vmstat for number of migrates pages (autonuma)", "yes", "numeric",  "counter", "/proc filesystem", ""
	"platform_vmstat_pgmigrate_success", "Virtual Memory stats based on /proc/vmstat for number of migrates pages (succeed)", "yes", "numeric",  "counter", "/proc filesystem", ""
	"platform_vmstat_pgmigrate_fail", "Virtual Memory stats based on /proc/vmstat for number of migrates pages (failed)", "yes", "numeric",  "counter", "/proc filesystem", ""
	"platform_vmstat_numa_hint_faults", "Virtual Memory stats based on /proc/vmstat for pgfaults for migration hints", "yes", "numeric",  "counter", "/proc filesystem", ""
	"platform_vmstat_numa_hint_faults_local", "Virtual Memory stats based on /proc/vmstat: pgfaults for migration hints (local)", "yes", "numeric",  "counter", "/proc filesystem", ""
	"platform_vmstat_pgfaults", "Virtual Memory stats based on /proc/vmstat:number of page faults", "yes", "numeric",  "counter", "/proc filesystem", ""
	"platform_pmm_bandwidth_reads", "Persistent memory module number of reads.", "auto (enable_perf_uncore)", "numeric",  "counter", "perf subsystem with dynamic PMUs (uncore)", "socket, pmu_type"
	"platform_pmm_bandwidth_writes", "Persistent memory module number of writes.", "auto (enable_perf_uncore)", "numeric",  "counter", "perf subsystem with dynamic PMUs (uncore)", "socket, pmu_type"
	"platform_cas_count_reads", "Column adress select number of reads", "auto (enable_perf_uncore)", "numeric",  "counter", "perf subsystem with dynamic PMUs (uncore)", "socket, pmu_type"
	"platform_cas_count_writes", "Column adress select number of writes", "auto (enable_perf_uncore)", "numeric",  "counter", "perf subsystem with dynamic PMUs (uncore)", "socket, pmu_type"
	"platform_upi_rxl_flits", "TBD", "auto (enable_perf_uncore)", "numeric",  "counter", "perf subsystem with dynamic PMUs (uncore)", "socket, pmu_type"
	"platform_upi_txl_flits", "TBD", "auto (enable_perf_uncore)", "numeric",  "counter", "perf subsystem with dynamic PMUs (uncore)", "socket, pmu_type"
	"platform_pmm_reads_bytes_per_second", "TBD", "no (enable_perf_uncore and enable_derived_metrics)", "numeric",  "gauge", "derived", "socket, pmu_type"
	"platform_pmm_writes_bytes_per_second", "TBD", "no (enable_perf_uncore and enable_derived_metrics)", "numeric",  "gauge", "derived", "socket, pmu_type"
	"platform_pmm_total_bytes_per_second", "TBD", "no (enable_perf_uncore and enable_derived_metrics)", "numeric",  "gauge", "derived", "socket, pmu_type"
	"platform_dram_reads_bytes_per_second", "TBD", "no (enable_perf_uncore and enable_derived_metrics)", "numeric",  "gauge", "derived", "socket, pmu_type"
	"platform_dram_writes_bytes_per_second", "TBD", "no (enable_perf_uncore and enable_derived_metrics)", "numeric",  "gauge", "derived", "socket, pmu_type"
	"platform_dram_total_bytes_per_second", "TBD", "no (enable_perf_uncore and enable_derived_metrics)", "numeric",  "gauge", "derived", "socket, pmu_type"
	"platform_dram_hit_ratio", "TBD", "no (enable_perf_uncore and enable_derived_metrics)", "numeric",  "gauge", "derived", "socket, pmu_type"
	"platform_upi_bandwidth_bytes_per_second", "TBD", "no (enable_perf_uncore and enable_derived_metrics)", "numeric",  "counter", "derived", "socket, pmu_type"
	"platform_last_seen", "Timestamp the information about platform was last collected", "yes", "timestamp",  "counter", "internal", ""



Internal metrics
================

.. csv-table::
	:header: "Name", "Help", "Enabled", "Unit", "Type", "Source", "Levels/Labels"
	:widths: 5, 5, 5, 5, 5, 5, 5 

	"wca_up", "Health check for WCA returning timestamps of last iteration", "yes", "timestamp",  "counter", "internal", ""
	"wca_information", "Special metric to cover some meta information like wca_version or cpu_model or platform topology (to be used instead of include_optional_labels)", "yes", "numeric",  "gauge", "internal", ""
	"wca_tasks", "Number of discovered tasks", "yes", "numeric",  "gauge", "internal", ""
	"wca_mem_usage_bytes", "Memory usage by WCA itself (getrusage for self and children).", "yes", "bytes",  "gauge", "internal", ""
	"wca_duration_seconds", "Internal WCA function call duration metric for profiling", "yes", "numeric",  "gauge", "internal", ""
	"wca_duration_seconds_avg", "Internal WCA function call duration metric for profiling (average from last restart)", "yes", "numeric",  "gauge", "internal", ""

