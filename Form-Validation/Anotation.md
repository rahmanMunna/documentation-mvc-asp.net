# Anotation:
- Nothing but ,set of rules that can be applied upon any field,class,action,api.
- Special attribute you apply to classes or their properties to add metadata, validation rules.
- Written in square brackets [ ]
  - Validate user input
  - Define database rules (Entity Framework)
  - Describe model metadata.
    
## `🧰 Namespace : ` `using System.ComponentModel.DataAnnotations`

## 🧠 Example : 
- `Description : ` Suppose we have a `User` class and has some field.
```
Class User{
  string Name {get;set;}
  string Email {get;set;}
  string Age {get;set;}
  string Password {get;set;}
}
```
- **To validate each field when set their value** ➡️ just apply anotation upon each field.

```
Class User{

  [Required]
  [StringLength(50)]
  string Name {get;set;}

  [EmailAddress]
  string Email {get;set;}

  [Range(1,100)]
  string Age {get;set;}

  [RegularExpression("pattern")]
  [StringLength(50, MinimumLength = 3)]
  string Password {get;set;}
}
```
- We can also use Regular expresion. But this is only works for `string` type.
## 🔍 How It Works:
- When a user submits a form:
  - ASP.NET automatically checks these annotations.
  - If any rule fails, validation errors are returned to the view.(if error message is set)
- We can also Set error message that will return when any validation rules failed
  
```
    [Required(ErrorMessage = "Name is required")]
    [StringLength(50, MinimumLength = 3)]
    public string Name { get; set; }

    [Range(18, 60, ErrorMessage = "Age must be between 18 and 60")]
    public int Age { get; set; }
```
## 🧱 Common Data Annotations:
| Annotation                                 | Purpose                                                  |
| ------------------------------------------ | -------------------------------------------------------- |
| `[Required]`                               | Makes a field mandatory                                  |
| `[StringLength(max, MinimumLength = min)]` | Limits length of strings                                 |
| `[Range(min, max)]`                        | Ensures numeric value is within range                    |
| `[EmailAddress]`                           | Validates email format                                   |
| `[Compare("Password")]`                    | Compares two fields (like password and confirm password) |
| `[Key]`                                    | Marks a property as the primary key (Entity Framework)   |
| `[Display(Name="Full Name")]`              | Changes the label text shown in the view                 |
| `[DataType(DataType.Date)]`                | Helps render proper input type (like date picker)        |
| `[RegularExpression("pattern")]`           | Validates data using regex                               |

- For Details : https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations?view=net-9.0
