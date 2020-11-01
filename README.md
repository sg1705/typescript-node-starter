# How to setup a Typescript Node project with grpc

# Step 1 — Initialize an npm project
`npm init -y`

# Step 2 — Initialize as TypeScript compiler
`tsc --init`

# Step 3 — Configure TypeScript compiler's outDir
```
{
  "compilerOptions": {
    .....
    .....
    "outDir": "./dist",
    ....
  }
}
```

# Step 4 — Create a build & start script in package.json

Let's put together a script to build the source code
```
{
  ....
  ....
  ....
  "scripts": {
    "build": "tsc --watch",
    "start" : "tsc && node dist/main.js",
  },
  ....
  ....
}
```

## Reference
This setup was inspired from a similar [writeup](https://www.digitalocean.com/community/tutorials/setting-up-a-node-project-with-typescript) on Digital Ocean. I have simplified it further and made a few changes.

* Remote the use of TSLint. TSLint is no longer maintained and eslint is the way to go
* Not all projects need express, so removed that dependency