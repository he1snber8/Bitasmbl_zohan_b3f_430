# Quickstart for Bitasmbl project (Blazor)

## 1) Install Bitasmbl-CLI package

```bash
npm i bitasmbl-cli
```

## 2) Run bitasmbl command to set up the project

```bash
bitasmbl pull --repoUrl  --appId 430 --repoId 276
```

## 3) Enter into the main directory and start coding!

```bash
cd 
```

## Customize requirements in a way you like

Bitasmbl organizes development into requirements. Each requirement describes a feature or implementation goal and can define suggested file locations through a `paths` array.

The `paths` property acts as a mapping guideline, helping contributors understand where related code should live.

You can customize `paths` mappings through the `bitasmbl.json` file.

{"Requirement":"Define portfolio layout","Paths":["**/src/layouts/**","**/src/components/layout/**","**/src/pages/**","**/src/routes/**","**/app/**"]}

## Requirement Evaluation

Bitasmbl includes a requirement evaluation workflow that lets contributors select a task and submit work for validation.

Run:

```bash
bitasmbl evaluate
```

Example output:

<pre>
? Available Requirements:

❯ [<span style="color:#9333ea">1</span>] <span style="color:#9333ea"> Define portfolio layout </span>            [3]
  [2] Build showcase components            [3]
  [3] Implement navigation routing         [3]
</pre>

`[x]` on the right represents the number of submission attempts remaining for a requirement.

## Example evaluation result

```razor
@*
|--------------------------------------------------------------------------
| BITASMBL EVALUATION
|--------------------------------------------------------------------------
| REQUIREMENT:
| Implement product catalog UI
|
| SCORE: 21/100
| STATUS: FAIL ✕
|
| INSIGHT:
| The component renders static product data and does not use a service,
| loading state, error handling, reusable components, or async data fetching.
|--------------------------------------------------------------------------
*@

@page "/products"

<h1>Products</h1>

<ul>
    @foreach (var product in products)
    {
        <li>
            <strong>@product.Name</strong> - $@product.Price
        </li>
    }
</ul>

@code {
    private List<Product> products = new()
    {
        new Product(1, "Keyboard", 89.99m),
        new Product(2, "Mouse", 49.99m)
    };

    private record Product(int Id, string Name, decimal Price);
}
```

## Learn More

For complete command references, workflow explanations, and additional documentation, visit:

👉 [Bitasmbl Documentation](https://bitasmbl.com/docs)
