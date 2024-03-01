# OptionalType
When it matters if there's a difference between "Null" and "Not present"

Supporting Optional Type is straightforward to use, and plays well with your existing type system.

<table>
<tr>
<td>Simple to Use!</td>
<td>Supports System.Text.Json</td>
</tr>
<tr>
<td>

``` C#
public class Person
{
    public Optional<string> FirstName { get; set; }
    public Optional<string> LastName { get; set; }
}
```
</td>
<td>

``` C#
var opts = new JsonSerializerOptions();
opts.AddOptionalType();
```

OR

``` C#
JsonSerializerOptions.Default.AddOptionalType();
```
</td>
</tr>
</table>

<table>
<tr>
<td>
Json
</td>
<td>
Now Use It!
</td>
</tr>
<tr>
<td>

``` JSON
{
    "FirstName" : "John"
    "LastName" : null
}
```
</td>
<td>

``` C#
person.FirstName.IsDefined == true;
person.FirstName == "John";

person.LastName.IsDefined == true;
person.LastName == null; //true
```
</td>
</tr>
<tr>
<td>

``` JSON
{
  "FirstName" : "John"
}
```
</td>
<td>

``` C#
person.FirstName.IsDefined == true;
person.FirstName == "John";

person.LastName.IsDefined == false;
person.LastName == null; //false
```
</td>
</tr>
</table>
