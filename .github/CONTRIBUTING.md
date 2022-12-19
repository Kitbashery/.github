## Contributing:
<p>
Code contributions should be submitted as a pull request to the development branch of a repository.
  
All code contributions are subject to the following requirements:

All C# code must be up to Microsoft's [C# Coding Conventions](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions). In the past Unity used conventions like using m_variableName and such practices can still be found in legacy code. However going forward Microsoft's conventions are now the standard.

---
### Code Comments & Markup:
  
In addition to the C# coding standards there is a prefered comment and region structure to follow.

* Encapsulate all properties in a #region labeled: Properties:
* Encapsulate all Monobehaviour Initializers, Updates, Gizmos and IEnumerators in a #region labeled: Initialization & Updates.
* Encapsulate Methods in a #region labeled: Methods: within this region you can have sub regions labeled to your liking.
* Triple slash summary comments must be used on all public methods and properties that are not obviously named. These summary comments corralate to the descriptions in the documentation.

```csharp
///<summary>
/// your summary...
///</summary>
YourMethod()
{
  //your code.
}
```
Sometimes when there is a private field/method that isn't very well named it is a good idea to add a summary comment there as well.

Additionally over any public property field that will be displayed in Unity's inspector window include:

```csharp 
[ToolTip("Your tooltip text")]
```

Sometimes with very obviouslty named fields that are self explanitory it isn't necessary to add a tooltip attribute, but in most cases it is prefered.

---
### Statements:
  
In some cases it is prefered to be more strict than Microsoft's conventions such as ```var``` is rarely if ever used, instead a known type should be used. Additionally when checking if statements ```== true/false``` is always used instead of ```if(variableName)``` These two practices are done to reduce ambiguity.

--- 
### Explictly declared property fields:
 
  Some properties in Unity are marked as Fields using attributes.
  
  ```csharp
   [field: SerializeField, Tooltip("Your tooltip text.")]
   public bool myVariable { get; set; } = false;
  ```
  This is typically done to expose an property to Unity's event system without adding additional boilerplate code. However note that the property name will appear in camelCase both in the inspector (Unity 2021+) and when referenced in code.
  
<i>I'm open to discussion about whether or not such properties should have an underscore added as a prefix or if the property should be PascalCase</i>

--- 
### If/Else Trees:
  
  If your if/else trees may become longer than 10-12 deep always use switch cases with enums or array indexes. This is because Unity's complier compiles switch cases more effeciently than long if/else trees beyond a certain depth*. 
  
---

### Documentation:
After putting in a pull request it is helpful (but not necessary) to also document them by putting in a pull request to The documentation repo and update the docs. Doing so however does not mean your additions/changes will be accepted so it may be best to add docs after your changes have been merged or let an official developer document the changes.

---
  
Code that deviates to far from these guidelines may not be merged untill it is revised and/or fits within the scope of the project.
  
  <i>*citation needed.</i>
</p>
