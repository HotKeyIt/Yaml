No idea what Yaml is, learn Yaml in 5 minutes: http://yaml.codeplex.com/wikipage?title=Yaml%20in%205%20minutes

Most of Yaml 1.2 specs are implemented: http://www.yaml.org/spec/1.2/spec.html

Though there are some things that I have changed and some do not work:

  - Tab character can be used to intend text as well as 2 spaces.
  - Only tags !!str, !!int, !!float, !!binary, !!bool and !!null are supported. !!set results in error and all other tags are ignored.
  - Only Yaml documents 1000 level deepness can be parsed (to increase simply increase [c]Loop 1000[/c] in [c]Load(ByRef txt,Y:=0)
  - Other features might be not implemented.
  - Yaml uses objects for map and arrays for sequence, however Dump will work for Array, Map and Object.

How to use:

  Create an Object from Text or File:
    `YamlObj:=Yaml(TextOrFilePath)`

  Apply/combine another Yaml document into existing object:
    `Yaml(TextOrFilePath, YamlObject)`

  Dump Yaml object back to text, use JSON from 5-th level only:
    `Yaml(YamlObject, 5)`

  Dump Yaml object back to text, use JSON only and indent until 5-th level (v1.0.4++):
    `Yaml(YamlObject, -5)`

  Yaml(TextOrFilePath) will result in Array of documents (objects), if you have only one document you can retrieve it directly:
    `YamlObj:=Yaml(TextOrFilePath)[1]`

Notes:
UMap is only available in AHK_H!!!