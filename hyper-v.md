## Disable Hyper-V
- Open powershell as admin.
- Run:
```powershell
Disable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V-All

bcdedit /set hypervisorlaunchtype off
```
