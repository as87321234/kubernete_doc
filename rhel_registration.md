## 🧾 Red Hat 9 Registration Summary

> 🔗 [Back to Main README](./README.md)

### 🔧 Setup Steps

1. **Check Version**
   ```bash
   cat /etc/redhat-release

2. **Subscription Manager**
   ```bash
    sudo subscription-manager register --username=<username> --password=<password>
    sudo subscription-manager attach --auto

    sudo subscription-manager repos --enable=rhel-9-for-x86_64-baseos-rpms
    sudo subscription-manager repos --enable=rhel-9-for-x86_64-appstream-rpms

    sudo dnf repolist

