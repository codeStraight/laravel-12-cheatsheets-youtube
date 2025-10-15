```markdown
# Laravel 12 Blade Subviews Cheatsheet

| Directive        | Usage Example                                      | Description |
|------------------|----------------------------------------------------|-------------|
| **@include**     | `@include('components.header')`                    | Inserts the specified subview file into the main template. |
| **@includeIf**   | `@includeIf('components.sideBar')`                 | Includes the subview only if the file exists, otherwise skipped. |
| **@includeWhen** | `@includeWhen($isLoggedIn, 'components.header')`   | Includes the subview only when the given condition is **true**. |
| **@includeUnless** | `@includeUnless($isLoggedIn, 'components.header')` | Includes the subview only when the given condition is **false**. |
| **@includeFirst** | `@includeFirst(['admin.header', 'components.header'])` | Attempts to include the first available subview in the list (fallback support). |

✅ Use these directives to build reusable, clean, and maintainable Blade templates for your Laravel applications.
```