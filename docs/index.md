# rondinif/pipeline-typescript
Create your first pipeline for a typescript project

<!-- why -->
## project's drivers 
I needed an simple anc basic example from which to learn how to create a [**build pipeline** on **azure devops**](https://docs.microsoft.com/it-it/azure/devops/pipelines/?view=azure-devops) from a **typescript project** , I didn't find any, I decided to create one myself

<!-- how -->
## how this sample was born
Luckily there is an [excellent guide](https://docs.microsoft.com/en-us/azure/devops/pipelines/create-first-pipeline) to create a similar thing for **javascript** projects  
with its [source code on github](https://github.com/MicrosoftDocs/pipelines-javascript)

and also [very simple and clear tutorials like this](https://itnext.io/step-by-step-building-and-publishing-an-npm-typescript-package-44fe7164964c)) are available to take flight with typescript

I simply put all togheter and I got one pipeline that works for typescript.

## how to 
- [build and test on your machine](./build-and-test-on-ide.md)
- [build and test on azure pipeline](./setup-build-and-test-azure-pipeline.md)

## Sample Typescript NodeJS application for Azure Pipelines

For information on how to set up a pipeline for this repository, see [Create your first pipeline](https://docs.microsoft.com/azure/devops/pipelines/get-started-yaml?view=azure-devops).




<!-- what -->
## what's changing from  [pipelines-javascript](https://github.com/MicrosoftDocs/pipelines-javascript)
with respect to commmit e34dc460c1562d3e9a5cd746dd89d6805fcc8b6b of [pipelines-javascript](https://github.com/MicrosoftDocs/pipelines-javascript) these are the main changes made to rise [pipelines-javascript](https://github.com/rondinif/pipelines-typescript):
- node modules ( packages )
    - added as dev dependecies ( `see package.json`)
        - `npm install --save-dev typescript`
        - `npm install --save-dev @typescript-eslint/eslint-plugin`
        - `npm install --save-dev @typescript-eslint/parser`
        - `npm install --save-dev jest`
        - `npm install --save-dev ts-jest`
        - `npm install --save-dev @types/jest`
        - `npm install --save-dev eslint`
        - `npm install --save-dev eslint-plugin-jest`
        - `npm install --save-dev @types/express`
        - `npm install --save-dev dotenv`
        - `src/__tests__/index.test.ts`
- sources 
    - add
        - `tsconfig.json`
        - `jest.config.js`
        - `src/index.ts`

    - remove 
        - `server.js`
        - `gulpfile.js`
        - `test/index.js`

    - changed
        - .gitignore ( + `'target'` )
        - package.json ( `"main": "target/index.js"`, `"build": "tsc"`, `"test": "jest"` and removed gulp,mocha,nyc deps that aren't used by this typescript sample )

## Licence
MIT