![](https://kitbashery.com/assets/images/kitbashery-github-banner.jpg)

<b>Kitbashery professionally develops & maintains a collection of Unity assets as a freemium service.</b>

## Installation Options:
<details open>
<summary>Options:</summary>
<pre>

1. The Unity Asset Store will have packages for the current Unity LTS version.
2. The most recent version can be downloaded from the asset's product page on <a href="https://kitbashery.com/">kitbashery.com</a>.
3. Legacy versions can be found in the asset's GitHub repository's Releases tab.
4. Copy the asset's GitHub repository's Clone HTTPS URL and paste it into the package manager.
5. Install via openUPM (click the badge on the asset's GitHub repo).
</pre>
</details>

## Contributing:
<p>
All code contributions are subject to the following requirements:

All C# code must be up to Microsoft's [C# Coding Conventions](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions). In the past Unity used conventions like using m_variableName and such practices can still be found in legacy code. However going forward Microsoft's conventions are now the standard.

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

In some cases it is prefered to be more strict than Microsoft's conventions such as var is rarely if ever used, instead a known type should be used. Additionally when checking if statements == true/false is always used instead of if(variableName) These two practices are done to reduce ambiguity.

After putting in a pull request it is helpful (but not necessary) to also document them by putting in a pull request to The documentation repo and update the docs. Doing so however does not mean your additions/changes will be accepted so it may be best to add docs after your changes have been merged or let an official developer document the changes.

Code that deviates to far from these guidelines may not be merged untill it is revised and/or fits within the scope of the project.
</p>
