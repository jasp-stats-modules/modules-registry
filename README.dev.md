## Dev notes

- JASP modules are first describes in a `yaml` file under `modules-metadata` directory. This file contains the module's name, description, and the path to the module's source code as shown in this snippet:

```yaml
name: "ModuleName"
gitUrl: "Your JASP module git repository"
```

- When a PR is opened a git workflow triggers, `check-meta-files`, where checks can be added.
- Merging will only add the new `yaml` file to the `modules-metadata` directory on `main` branch.
- To fork and create submodules the workflow `process-new-meta-files` should be triggered manually.
- The `process-new-meta-files` workflow need a PAT with organization content write permissions and saved in organization secret `ORG_PAT`.
- The `process-new-meta-files` workflow will parse the `yaml` files and create forks of the remote JASP modules locally. It will also add submodules to the the `beta-modules` folder.

### Sequence diagram

```mermaid
sequenceDiagram
    title Submitting a new Jasp Module

    participant JaspTemplate as jasp-stats/jaspModuleTemplate
    participant UserModule as user/myJaspModule
    participant JaspModules as jasp-stats-modules/modules-registry
    participant UserModules as user/modules-registry
    participant JaspMyModule as jasp-stats-modules/myJaspModule

    JaspTemplate->>UserModule: fork
    UserModule->>UserModule: create module
    JaspModules->>UserModules: fork
    UserModules->>UserModules: create myJaspModule.yaml file
    UserModules-->>JaspModules: open PR
    JaspModules->>JaspModules: trigger check workflow
    JaspModules->>JaspModules: review PR
    JaspModules->>JaspModules: merge PR
    JaspModules->>JaspModules: manually trigger 'process-new-meta-files.yml' workflow
    JaspModules->>UserModule: prepare to fork locally
    UserModule->>JaspMyModule: fork
    JaspModules->>JaspMyModule: add as submodule to JaspModules/beta-modules

```
