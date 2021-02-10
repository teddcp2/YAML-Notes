# YAML Notes

- A data serialization language like XML or JSON. ([yamls vs json](https://stackoverflow.com/q/1726802/12210002))
- data serilization means different applications written in different languages can interchange their data based on a common data strucutre...
- YAML > Yet Another Markup Language / YAML Aint Markup Language
- file extensions are '''.yaml or .yml'''

## Different Notations

- Key-value pairs and comments

```
# A comment can be added like this...
app: user-authentication
port: 9000
version: 1.7
```

- Objects

```
microservice:
  app: user-authentication
  port: 9000
  version: 1.7
```

- Lists/ Arrays - via hyphens or [ele1, ele2, ...]

```
microservice:
  -
    app: user-authentication
    port: 9000
    version: 1.7
  -
    app: Client-app
    port: 9001
    version: 2
```

- We can use boolean values as well

```
app :
    deployed : true
    working : off
    checked : yes
```

- We can use multiline strings with pipe and >. The difference is that the latter one will make the input into one line like a para.

```
app : |
    This is a multi-line string
    and it continues to next line
    ....

app2: >
    a Multi-line comment
    which will be written as
    a paragraph / one line...
```

- We can refer some env vars with $ and placeholders as {{ }}

```
region : $exported_aws_region
value : {{ home.app.value }}
```

- we can define multiple yaml files into one by ---

```
app: user-authentication
port: 9000
version: 1.7
---
app: Client-app
port: 9001
version: 2
```

- we can refer defined values with anchors i.e \*var and &var

```
name : &app-name ui
version : 2.1
id : *app-name

```

- we can refer the entire object too ...

```
app : &app-reference
    deployed : true
    working : off
    checked : yes

foo :
    <<: *app-reference

```

### Extra links

- Youtube links
  - [link1](https://youtu.be/1uFVr15xDGg) **RECOMMENDED**
  - [link2](https://youtu.be/cdLNKUoMc6c)
- blogs

  - [link1](https://dev.to/paulasantamaria/introduction-to-yaml-125f) **RECOMMENDED**
  - [link2](https://dev.to/javanibble/yaml-essentials-520b)

- **Pythonic** >> There is **[pyyaml](https://pyyaml.org/wiki/PyYAMLDocumentation)** package to load the yaml files...
  - [link](https://dev.to/developertharun/yaml-tutorial-using-yaml-with-python-pyyaml-443d#why-yaml)

Thanks for Reading
Tedd :)
