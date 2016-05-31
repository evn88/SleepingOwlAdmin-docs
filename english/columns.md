# Table columns

Creating new column in a table which show list of notes.

**Example**

```php
AdminDisplay::table()
    ->setColumns([
        AdminColumn::link('title')->setLabel('Title'),
        AdminColumn::datetime('date')->setLabel('Date')->setFormat('d.m.Y')->setWidth('150px')
    ])
```

Class `SleepingOwl\Admin\Display\TableColumn`, which Extends (it parent) all columns, are realise next interfaces:
`Illuminate\Contracts\Support\Arrayable` and
`Illuminate\Contracts\Support\Renderable`

In the coluumn clases used next trait [HtmlAttributes](html_attributes.md),
With this trait you can configure HTML attributes.

## Supported types

 - `AdminColumn::action($name)`
 - `AdminColumn::checkbox()`
 - `AdminColumn::count($name)`
 - `AdminColumn::custom()`
 - `AdminColumn::datetime($name)`
 - `AdminColumn::email($name)`
 - `AdminColumn::string($name)`
 - `AdminColumn::link($name)`
 - `AdminColumn::relatedLink($name)`
 - `AdminColumn::lists($name)`
 - `AdminColumn::image($name)`
 - `AdminColumn::order()`
 
## Column title

Every tables column have title and keep like own class
`SleepingOwl\Admin\Contracts\Display\TableHeaderColumnInterface`

**Example of work with title**

```php
...
    ->setColumns([
        ...
        AdminColumn::link('title')
            ->setLabel('Title')
            ->setOrderable(false),
        ...
    ]);
```

**Or directly work with title class**
```php
...
    ->setColumns([
        ...
        $link = AdminColumn::link('title')
        ...
    ]);
    
    $link->getHeader()
        ->setTitle('Title')
        ->setOrderable(false)
        ->setHtmlAttribute('class', 'bg-success text-center')
        ->setHtmlAttribute('data-tooltip', 'Test tooltip');
```

## Prohibition for sorting by column:
```php
AdminColumn::link('title')->setOrderable(false);
```
