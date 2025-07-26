# Recieve Data form `Form`
- Use name attribute to retrive value from input tag at server-end.
## There are 4 ways to access or retrive form data : 
1. Http `Request` base instance :
   - Applicable for all Asp.Net app
   - It aslo contains all `request related attributes`
   - `Request` is a controller instance.
     - This is a dictionary type
     - We can access in both `View` and `Controller` by `Request` object.
### Syntax : `Request["name"]`
----
### Example : 
- `View`
```html
create.cshtml

<input type="email" name="email">
```
- Access : in  `Controller`

```cs
public ActionResult Create()
{
    String email = Request["email"];
}
```
