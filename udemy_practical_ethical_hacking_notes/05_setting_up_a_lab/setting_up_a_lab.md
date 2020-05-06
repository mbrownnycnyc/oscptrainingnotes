# setting up a lab

## stop wasting time

One of the things I see over and over again on various reddits are people spending time trying to do things that are unnecessarily complex for them to reach their goals.  Just today I saw a guy posting about running `shellter` on `wine` in `kali`, and it failing.  Dude, stop _wasting your time_... why?  Why are you doing this?  Trust me, it's cool to run `kali` for everything, but you know what's cooler?  Compiling binaries with `shellter` easily... this means doing it on a Windows instance.

Stop wasting time.  Get to your goal via the path of least resistance, most quickly and with the least amount of errors by lowering your risk of failures.

## vmware player / install kali

1. Yes, don't bother with virtualbox.  Use vmware player.
2. Download vmware workstation player from here: https://www.vmware.com/products/workstation-player.html
3. Download kali ISO from here: https://www.kali.org/downloads/
4. Review kali notes to find out which kernel version is used in the kali image you downloaded: https://www.kali.org/kali-linux-releases/
5. Disable credential and device guard: https://docs.microsoft.com/en-us/windows/security/identity-protection/credential-guard/credential-guard-manage#disable-windows-defender-credential-guard
```
    HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\DeviceGuard dword:EnableVirtualizationBasedSecurity=0x0
    HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\DeviceGuard dword:EnableVirtualizationBasedSecurity=0x0
    HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\LSA dword:LsaCfgFlags=0x0
    bcdedit /create {0cb3b571-2f2e-4343-a879-d86a476d7215} /d "DebugTool" /application osloader
    bcdedit /set {0cb3b571-2f2e-4343-a879-d86a476d7215} path "\EFI\Microsoft\Boot\SecConfig.efi"
    bcdedit /set {bootmgr} bootsequence {0cb3b571-2f2e-4343-a879-d86a476d7215}
    bcdedit /set {0cb3b571-2f2e-4343-a879-d86a476d7215} loadoptions DISABLE-LSA-ISO,DISABLE-VBS
    bcdedit /set hypervisorlaunchtype off
```
6. Create a VM, applying the proper linux kernel version,put it in NAT mode for now, then install as you wish. I prefer using LVM.

7. yes, it will take a long time for the kali install the complete.