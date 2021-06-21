## ADoc cheatsheet

https://powerman.name/doc/asciidoc

## Generating documentation

From the root of the repository, run one of the following commands:
 
asciidoctor --base-dir docs/ --backend=html5 -o ../docs/index.html -w --doctype=book -a toc2 docs/boilerplate/index.adoc
asciidoctor --base-dir docs/ --backend=html5 -o ../docs/index.html -w --doctype=book -a toc2 -a production_build docs/boilerplate/index.adoc


The first command will build a development version of the guide, where the parts to be edited by the Partner are separated from the boilerplate. The second command will build a production version of the guide. In either case, the generated doc will be located at /docs/index.html. 

aws s3 cp docs/index.html s3://anton-fhir --acl public-read
aws s3 cp docs/images s3://anton-fhir/images --recursive --acl public-read

https://anton-fhir.s3.amazonaws.com/index.html


 
Also, this locally-generated version won’t have the parameter tables, since they are generated as part of the GitHub action.

