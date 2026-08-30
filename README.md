**Windows 11 Resource Monitoring**

Windows 11 lab using Task Manager and Resource Monitor to observe system activity, identify resource usage, and validate recovery.

**Resource Baseline**

- Resource Monitor establishes the system baseline before the test workload begins.
- CPU usage is low at about 13%, showing the system is relatively idle.
- This baseline provides a reference for comparing CPU usage during the Defender scan.

![Resource Baseline](images/01%20Resource%20Baseline.png)

**Process Baseline**

- Task Manager shows about 11% CPU and 27% memory usage before the workload begins.
- No single process is consuming a large amount of CPU or disk resources.
- Antimalware Service Executable is present but shows 0% CPU activity.

![Process Baseline](images/02%20Process%20Baseline.png)

**Workload Activity**

- A Microsoft Defender scan increases total CPU usage to about 54%.
- Antimalware Service Executable becomes the primary CPU consumer at about 47.5%.
- The process also generates measurable disk activity during the scan.

![Workload Activity](images/03%20Workload%20Activity.png)

**Process Analysis**

- Resource Monitor identifies `MsMpEng.exe` as the Microsoft Defender process responsible for the workload.
- The process uses about 46% CPU during the scan.
- Average CPU for `MsMpEng.exe` rises to about 15.21, confirming sustained activity during the observation period.

![Process Analysis](images/04%20Process%20Analysis.png)

**Process Recovery**

- After the Defender scan finishes, total CPU usage falls to about 6%.
- Antimalware Service Executable returns to 0% CPU usage.
- Disk and network activity also return to an idle state.

![Process Recovery](images/05%20Process%20Recovery.png)

**Recovery Validation**

- Resource Monitor confirms that overall CPU usage has returned to about 8%.
- `MsMpEng.exe` shows 0 current CPU usage and an average CPU value of about 0.16.
- Disk and network activity return to 0 while memory remains near the original 26% baseline.

![Recovery Validation](images/06%20Recovery%20Validation.png)

**Navigation**

[`Back to GitHub Profile`](https://www.github.com/cbueker-it)
