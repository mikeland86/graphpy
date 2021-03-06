# graphpy

### Python graph DB ORM

graphpy is a migration free plug and play ORM for any Python project. It was inspired by the graph db module from [graphp](https://github.com/mikeland86/graphp). It allows you to build quick and dirty db based models using a graph abstraction on top of MySQL.

A simple example:

### Define nodes (your model) with minimum boilerplate

```python
class User(GPNode):
    node_data = {
        'name': '',
        'last_name': '',
    }
```    
    
```python
# Use the model:
me = User(last_name='Doe')
me.set_name('Mike')
me.get_name()         # Mike
me.get_last_name()    # Doe
try:
    me.get_foo()      # throws exception
except: 
    me.get('foo')     # this is fine, returns None
me.set('foo', 'bar')  # it's fine to use non-declared data
me.get('foo')         # bar
me.save()
```

```python
# retrieve it from db:
me = User.get_by_id(123)
```

### Edges
*todo*

### Indexed data
*todo*

*graphpy is a work in progress*

