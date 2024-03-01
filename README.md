# OptionalType
When it matters if there's a difference between "Null" and "Not present"

<table>
    <tr>
        <td>C# Object</td>
        <td>JSON</td>
        <td>Deserialized As</td>
    </tr>
    <tr>
        <td>
        ``` C#
        public class Person()
        {
            public string FirstName { get; set; }
            public Optional<string> LastName { get; set; }
        };
        ```
        </td>
        <td>
        ``` JSON
        {
            "FirstName":"John"
        }
        ```
        </td>
        <td>
        ``` C#
            person.FirstName == "John"; //true
            person.LastName.IsDefined == false; //true            
        ```
        </td>
    </tr>
</table>