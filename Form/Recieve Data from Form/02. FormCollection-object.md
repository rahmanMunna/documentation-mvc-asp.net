# 2. FormCollection Object :
- Recieve an object of `FormCollection` as a parameter in submitting methode (**Which action methode responsible for after submitting form**)
## Example : 
- Suppose, in `UserController`,  `Create` action methode is responsible to handle request after submmitting the form
```cs
UserController.cs

public ActionResult Create(FormCollection obj)
{
    obj["name"]; // access the value
}
```
- This is only applicable for `.Net MVC`
- This only hold Form data, nothing else
- FormCollection object is also an dictionary.
