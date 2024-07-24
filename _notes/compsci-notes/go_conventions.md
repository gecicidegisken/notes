---
title : go: conventions
feed: show
date : 16-05-2024
tags: ["golang"]
summary:  Conventions for writing Go code
---

### **naming**

> Use short names.
> 
> 
> Think about context.
> 
> Use your judgment.
> 
- Use `MixedCase or camelCase`
    - Don’t use `names_with_underscore`
- Acronyms should be all capitals
    - `⁠ServeHTTP` ⁠ or `⁠IDProcessor`⁠
- Keep **local variables** short
    - prefer i to index

prefer r to reader

prefer b to buffer
- Prefer `count` to `runeCount` inside a function named `RuneCount`.

- Exported names are qualified by their package names.
    - That’s why we have `bytes.Buffer` and `strings.Reader`,
    not `bytes.ByteBuffer` and `strings.StringReader`.
- Exported names start with capital letter, so that they can be used in other packages.
- Keep **package names** short, don’t use underscores
- **Test files** end in `⁠_test.go`⁠

Also check: [clean code](clean%20code.md)

---

### **project layout**

**package**

All the files in a package live in a single directory. Packages collect related code.

**`/internal`**

This is the code you don’t want others importing in their applications or libraries. Enforced by Go compiler.

`⁠**/pkg**`

⁠Can be used by external applications. Other projects will import these libraries expecting them to work.

- `*⁠/vendor**`

⁠Application dependencies.

The `go mod vendor` command will create the `/vendor` directory for you.

**⁠⁠`⁠/configs`⁠**

Configuration file templates or default configs.

`⁠**/test**⁠` ⁠

Additional external test apps and test data. Feel free to structure the `/test` directory anyway you want. For bigger projects it makes sense to have a data subdirectory.

**⁠**

Reference here: [https://github.com/golang-standards/project-layout?tab=readme-ov-file](https://github.com/golang-standards/project-layout?tab=readme-ov-file)

---