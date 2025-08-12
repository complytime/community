# ComplyTime Installation


## What You'll Need

* MacOS
* Linux machines
* Release downloads

### Useful commands

#### Getting the OSCAL Content

* Fork the  [`ComplianceAsCode/oscal-content`](https://github.com/ComplianceAsCode/oscal-content) repository.

* Clone the repository using `git clone git@github.com:ComplianceAsCode/oscal-content.git`.

* Ensure that you run the command `git remote add upstream git@github.com:ComplianceAsCode/oscal-content.git` to ensure that your fork can easily stay up-to-date with the upstream.

```bash
# Copying OSCAL Catalogs from oscal-content 
cp ~/{path-to-your-forked-oscal-content}/catalogs/ -r ~/.local/share/complytime/bundles/

# Copying OSCAL Profiles from oscal-content
cp ~/{path-to-your-forked-oscal-content}/profiles/ -r ~/.local/share/complytime/controls/

# Copying OSCAL Component Definitions from oscal-content
cp ~/{path-to-your-forked-oscal-content}/component-definitions/ -r ~/.local/share/complytime/controls/
```

The ~/.local/share/complytime/bundles and controls/ will hold the catalog.json, profile.json, and the component-definition.json that will allow for use with the complyctl commands.




```shell
make build
export COMPLYTIME_DEV_MODE=1
```

```bash
./bin/complyctl list # See the available frameworks
./bin/complyctl info <framework-id> 
./bin/complyctl plan <framework-id> --dry-run # See default assessment plan contents
./bin/complyctl plan <framework-id> --dry-run --out config.yml # Create a config file to edit assessment plan
./bin/complyctl plan <framework-id> --scope-config config.yml # Write assessment plan to workspace

```

#### Example OSCAL Content

[ANSSI catalog.json](https://github.com/ComplianceAsCode/oscal-content/blob/main/catalogs/anssi/catalog.json)

[RHEL10 ANSSI Minimal profile.json](https://github.com/ComplianceAsCode/oscal-content/blob/main/profiles/rhel10-anssi-minimal/profile.json)

![rhel10 anssi catalog](https://github.com/hbraswelrh/community/blob/docs/community-template/docs/img/img/catalog.png?raw=true)

> Once the profile content has been copied to `~/.local/share/complytime/controls/profile.json` ensure the href is "file://controls/{name-of-catalog}.json"

![rhel10 anssi minimal profile](https://github.com/hbraswelrh/community/blob/docs/community-template/docs/img/img/profile.png?raw=true)

[RHEL10 ANSSI Minimal component-definition.json](https://github.com/ComplianceAsCode/oscal-content/blob/main/component-definitions/rhel10/rhel10-anssi-minimal/component-definition.json)

![rhel10 anssi minimal component definition](https://github.com/hbraswelrh/community/blob/docs/community-template/docs/img/img/compdef.png?raw=true)

> Once the component definition content has been copied to `~/.local/share/complytime/bundles/component-definition.json` the href should be the following: "file://controls/{name-of-profile}.json"

**`complyctl info --limit 5`**

![info](https://github.com/hbraswelrh/community/blob/docs/community-template/docs/img/img/info.png?raw=true)

**`complyctl info --control r30 --limit 5`**

![info control](https://github.com/hbraswelrh/community/blob/docs/community-template/docs/img/img/info-control.png?raw=true)

**`complyctl info --rule set_password_hashing_algorith_systemauth`**

![info rule](https://github.com/hbraswelrh/community/blob/docs/community-template/docs/img/img/info-rule.png?raw=true)

**`complyctl info --parameter var_accounts_maximum_age_root`**

![info parameter](https://github.com/hbraswelrh/community/blob/docs/community-template/docs/img/img/info-parameter.png?raw=true)
