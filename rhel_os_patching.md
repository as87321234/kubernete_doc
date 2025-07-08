## How to Patch a RHEL 9.6 System

> 🔗 [Back to Main README](./README.md)

Follow these steps to patch a Red Hat Enterprise Linux (RHEL) 9.6 system:

### 1. Update Repository Metadata

```bash
sudo dnf clean all
sudo dnf makecache
```

### 2. Check for Available Updates

```bash
sudo dnf check-update
```

### 3. Apply All Updates

```bash
sudo dnf update -y
```

### 4. Reboot if Required

Some updates (like kernel or system libraries) may require a reboot:

```bash
sudo reboot
```

### 5. Verify System Status

After reboot, check the system status and confirm updates:

```bash
cat /etc/redhat-release
dnf history
```

### Notes

- Ensure you have a valid Red Hat subscription (`subscription-manager status`).
- Consider testing updates in a staging environment before applying to production.
- For security updates only, use:  
    ```bash
    sudo dnf update --security -y
    ```

Refer to the [official RHEL documentation](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/9/) for more details.