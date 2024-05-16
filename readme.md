# ShareX Group Policy Template

## Summary
Group Policy files for ShareX (https://getsharex.com/) -or- (https://github.com/ShareX/ShareX)

## Installation
Copy the files in the `PolicyDefinitions` folder to your `PolicyDefinitions` folder at `C:\Windows\PolicyDefinitions` for Local Group Policy. Copy to `\\yourdomain.local\SYSVOL\yourdomain.local\Policies\PolicyDefinitions` if using the group policy central store in your domain.

## Configuration
In the Group Policy Editor (`gpedit.msc` for local group policy, `gpmc.msc` for domain group policy):  

```
Local Computer Policy || GPOName [SERVER.DOMAIN.TLD]/
├── Computer Configuration/
│   └── Administrative Templates/
│       └── ShareX/
│           ├── Allow Saving Logs to Disk
│           ├── Personal Path
│           ├── Auto-Update Check
│           └── Upload Capability
└── User Configuration/
    └── Administrative Templates/
        └── ShareX/
            ├── Allow Saving Logs to Disk
            ├── Personal Path
            ├── Auto-Update Check
            └── Upload Capability
```

> [!NOTE]  
> Due to the location of the ShareX registry keys (`Software\ShareX` vs `Software\Policies\ShareX`), these settings are considered a `preference` and not a `policy`, meaning setting them back to "Not Configured" will NOT delete the existing registry key if one had previously been set by the group policy. This is a design choice made by the creators of ShareX which will hopefully be addressed in the future.