# Organization and Productivity
## Logseq
* GitHub Repository: https://github.com/logseq/logseq

```bash
# Download and run the installer
curl -fsSL https://raw.githubusercontent.com/logseq/logseq/master/scripts/install-linux.sh | bash

# Or install a specific version
curl -fsSL https://raw.githubusercontent.com/logseq/logseq/master/scripts/install-linux.sh | bash -s -- 0.10.14

# For user-specific installation (no root required)
curl -fsSL https://raw.githubusercontent.com/logseq/logseq/master/scripts/install-linux.sh | bash -s -- --user
```
### Error EPERM: operation not permitted 
The Error: EPERM: operation not permitted in Logseq typically indicates a file permission conflict or a file locking issue where the application cannot write to or modify files in your vault.  This error manifests differently depending on the context:

File Writing Errors: Occurs when Logseq cannot save changes to .md files or internal data files (e.g., graphs-txid.edn). This is frequently caused by OneDrive sync conflicts on Windows, where the cloud service locks the file during upload, or by the "Automatically change file permissions" setting in Logseq's Advanced options. 
Plugin/Theme Installation Errors: Occurs when Logseq cannot rename or move files from the temporary download folder to the plugins directory. This is often due to antivirus software or Windows Explorer having a file handle open on the target directory, preventing the move operation. 
Vault Access Errors: Occurs when Logseq cannot read the entire graph directory (e.g., scandir error), often due to the vault being stored in a protected system directory or having incorrect user ownership permissions. 

**Common Solutions**
* Disable Automatic Permission Changes: Go to Options > Advanced and uncheck "Automatically change file permissions".  This often resolves chmod related EPERM errors on Windows.
