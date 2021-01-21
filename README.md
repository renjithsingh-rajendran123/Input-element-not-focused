# Input-element-not-focused
Input element not focused when calling FocusAsync in wasm application


I have an issue in which the Input element is not focused at initial rendering when calling FocusAsync. Always the browser's url tab is getting focused on initial rendering.

**Note :** This works fine in Server app(input element focused properly). Only in wasm i am getting this issue.

Please refer the code which i have used 

`@page "/"

<input type="text" @ref="myref" />

@code {

    private ElementReference myref;

    protected override async Task OnAfterRenderAsync(bool firstRender)
    {
        if (firstRender)
        {
            await myref.FocusAsync();
        }
    }
}`

