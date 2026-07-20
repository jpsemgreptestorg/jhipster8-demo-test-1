# Maven and npm test fixture

This repository is an independent test copy of
[`mraible/jhipster8-demo`](https://github.com/mraible/jhipster8-demo), created
for Semgrep Plumbline multi-ecosystem testing.

It includes the upstream npm lockfile plus two generated Maven dependency
artifacts:

- `package-lock.json` — npm's resolved dependency lockfile.
- `maven_dep_tree.txt` — Maven's hierarchical dependency tree.
- `.mandoline/maven-deps.txt` — Maven's flat resolved dependency closure in
  the format consumed by Mandoline and Plumbline.

Maven does not define a standard lockfile. Regenerate the committed Maven
artifacts from the repository root with:

```bash
./mvnw dependency:tree \
  -DoutputFile=maven_dep_tree.txt \
  -DappendOutput=false

mkdir -p .mandoline
./mvnw dependency:list \
  -DoutputFile=.mandoline/maven-deps.txt \
  -DappendOutput=false \
  -DincludeScope=runtime
```

The Maven artifacts were generated from upstream commit `a338150`.
