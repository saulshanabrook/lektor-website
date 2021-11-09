# Updating Diplays in Jupyter


https://user-images.githubusercontent.com/1186124/140978056-55a95932-862e-4395-b2e5-dbbed16cb295.mov

In Jupyter you can make a new display handle with `IPython.display.diplay(obj, display_id=True)`. This lets you update a display, without writing any JS or relying on Jupyter widgets. 

For example, to print some html in a notebook you can do:

```python
from IPython.display import HTML, display

handle = display(HTML("hi"), display_id=True)
```

This will display the HTML in the output. Then later on, you can update the display, which will update the output:

```python
handle.update(HTML("there"))
```

If you want to re-display it in another cell, you can use `handle.display`:

```python
handle.display(HTML("hi again!"))
```

This will update the previous representation and show a new one that will also be linked!

```python
handle.update(HTML("final update"))
```
