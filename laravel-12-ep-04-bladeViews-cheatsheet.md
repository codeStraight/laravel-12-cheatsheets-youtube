| Topic | Syntax / Example | Explanation |
|-------|------------------|-------------|
| **Create View** | `php artisan make:view products.index` | Creates `resources/views/products/index.blade.php`. |
| **Return View from Controller** | `return view('products.index');` | Returns the Blade view from controller. |
| **Pass Data with compact()** | `return view('products.index', compact('products'));` | Passes controller data to the view. |
| **Debug Data** | `@dd($products)` | Dumps & dies, useful for debugging. |
| **JSON/Print Raw Data** | `{{ json_encode($products) }}` or `<pre>{{ print_r($products, true) }}</pre>` | Displays raw array data. |
| **Blade Loop** | `@foreach($products as $product) ... @endforeach` | Loops through data. |
| **Curly Braces** | `{{ $product['title'] }}` | Escaped output (safe from XSS). |
| **Blade Comments** | `{{-- Comment --}}` | Comment inside Blade, not visible in HTML. |
| **@php Directive** | `@php $time = date('h:i A'); @endphp` | Execute inline PHP code. |
| **Raw PHP** | `<?php echo date('Y-m-d'); ?>` | Insert PHP directly into Blade. |
| **If Statement** | `@if(...) ... @else ... @endif` | Conditional rendering. |
| **Switch Statement** | `@switch($role) @case('admin')...@endswitch` | Multiple condition checks. |
| **$loop->index** | `{{ $loop->index }}` | Current iteration (starts at 0). |
| **$loop->iteration** | `{{ $loop->iteration }}` | Current iteration (starts at 1). |
| **$loop->remaining** | `{{ $loop->remaining }}` | Remaining iterations. |
| **$loop->first / $loop->last** | `@if($loop->first)...@endif` | Detect first/last iteration. |
| **$loop->count** | `{{ $loop->count }}` | Total number of loop items. |
| **$loop->even / $loop->odd** | `@if($loop->even)...@endif` | Detect odd/even iteration. |