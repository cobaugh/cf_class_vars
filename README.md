# cf_class_vars
CFEngine class_vars

## Usage
Create a directory within your masterfiles. Set `g.class_vars` to the path to this directory.

Place `.json` or `.yaml` (`.yml` extension support is coming in cfengine-3.11) files named after a class you want to match in this directory.

Call `class_vars` common bundle early in the bundlesequence.

Class vars files contain a json or yaml document, where the top-level keys are names of variables you wish to set. Files with higher precedence can override lower ones.

Order of precedence:
* "any"
* everything else
* "group_.+"
* "$(sys.fqdn)"

Additionally, a class named `has_cv_varname` is defined for every variable defined.

