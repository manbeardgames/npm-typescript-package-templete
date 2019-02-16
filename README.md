# Templete For NPM Package Using Typescript
This is just a templete that I use as a basis for creating NPM packages using TypeScript.

## Development Modules
The following modules are included using the `--save-dev` flag

| Module | Description | URL |
|---|---|---|
| typescript| Adds support for Typescript and compiling it | https://www.npmjs.com/package/typescript |
| prettier | Code formatter | https://www.npmjs.com/package/prettier | 
| tslint | Linting for Typescript | https://www.npmjs.com/package/tslint |
| tslint-config-prettier | Resolves issues that occur when using both tslint and prettier together | https://www.npmjs.com/package/tslint-config-prettier |
| jest | Javascript testing suite | https://www.npmjs.com/package/jest |
| ts-jest | Preprocessors that allows jest to work with Typescript | https://www.npmjs.com/package/ts-jest |
| @types/jest | Type definitions for jest | https://www.npmjs.com/package/@types/jest |

# Scripts
The following scripts are configured in `pacakage.json`
| Script | Command | Description |
|---|---|---|
| test | `npm test` | Executes all tests that are in the `/src/__tests__` directory |
| build | `npm run build` | Compiles the Typescript in the `/src` directory |
| format | `npm run format` | Runs the Prettier code formatter against the code |
| lint | `npm run lint` | Executes tslint against the code |
| prepare | Runs before the package is packed and published, and also on local `npm install`  | When executed, will build our source |
| prepublishOnly | Runs BEFORE `prepare` and ONLy on `npm publish` | When executed, this will run our configured tests and linting to make sure we don't publish bad code. |
| preversion | Runs before bumping a new package version with `npm vesion` | WHen executed, thi will run linting to ensure we're not bumping the version up with bad code |
| version | `npm version [<newversion> \| major \| minor \| patch \| premajor \| preminor \| prepatch \| prerelease [--preid=<prerelease-id>\ \| from-git]` | When a new version is bumped, after it's bumpted, the script will execute. The script will run the formatter against our code so no ugly code is commited and then perform a `git add-A src` |
| postversion | This will run AFTER bumping the pacakge version, and AFTER commit | This will push the commit and the tags |


