## js-mv

Move JavaScript files with import syntax

- Fixes relative imports on the file being moved/renamed
- Fixes imports on those files referencing the file being moved/renamed
- Fixes renames variables referencing the import if the filename was changed

## Installation

```
npm install -g jscodeshift
cd path/to/project
npm install eslint --save-dev
npm install refactoring-codemods --save-dev
cp path/to/js-mv .
chmod 755 js-mv
```

## Usage

```
cd path/to/project
./js-mv someFolder/someFile.js anotherFolder/anotherFile.js
```

Already moved the file? That's ok. Just specify the old path and the new path as you normally would.

## Caveats

- must run from root of project
- assumes camelCase files/directories
- Cannot move/rename folders at this time.
- Must specify full target file. (`./js-mv someFolder/someFile.js anotherFolder/`) won't work at this time.
- Uses .gitignore as a safeguard against performing a lint fix against unwanted files.  Change this if you'd rather use your .eslintignore.
- Double check the --ignore-pattern argument for your project
- Does not work on files with decorators
