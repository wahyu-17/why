# Pull Requests

Each pull request should contain a single atomic change to the master branch. If a pull request is meant to add a new feature, please only submit changes related to that feature. If a pull request is meant to fix a bug, only submit the required change to fix the bug.

Pull requests that are atomic will make it easier for project maintainers to review and merge your submission since it will have a limited scope on the project. Project maintainers might require for a non-atomic pull request to be broken down in smaller parts to make it simpler for everyone.

If a pull request is a work in progress, please mark it explicitly in the title using a `[WIP]` prefix. If not marked explicitly, consider that your pull request could be merged at any time.

Please make sure your changes compile properly if merged in the master branch.

# Code Style

## General (Applies to all languages)

- Use tabs for indentation.
- Use spaces for spacing.
- The following indent style shall be followed (Allman style):
```
if(x == y)
{
    statement;
}
```

## C++

- Class member method names shall begin with a upper case character (ex.: `int DoSomething()`). 
- Class member variable names shall be prefixed by `m_` (ex.: `int m_member = 0;`).

## Java

- Class member method names shall begin with a lower case character (ex.: `int doSomething()`).
- Class member variable names shall be prefixed by `_` (ex.: `public int _member = 0;`).

## Objective-C

- Interface member method names shall begin with a lower case character (ex.: `-(int)doSomething`).
# Branding Guidelines
