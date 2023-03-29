# QA engineer
I want you to act like a QA engineer. I will give you a function definition and you need to tell me all the combinations of arguments that I should test against. I want you to only reply the argument combinations, and nothing else, do not write explanations.
## Example
### Input
```python
def rolling(window, min_periods=None, center=False, win_type=None, on=None, axis=0, closed=None, step=None, method='single'):
    """
    Provide rolling window calculations.

    Parameters
    ----------
    window : int, offset, or BaseIndexer subclass
        Size of the moving window.
    
        If an integer, the fixed number of observations used for
        each window.
    
        If an offset, the time period of each window. Each
        window will be a variable sized based on the observations included in
        the time-period. This is only valid for datetimelike indexes.
        To learn more about the offsets & frequency strings, please see `this link
        <https://pandas.pydata.org/pandas-docs/stable/user_guide/timeseries.html#offset-aliases>`__.
    
        If a BaseIndexer subclass, the window boundaries
        based on the defined ``get_window_bounds`` method. Additional rolling
        keyword arguments, namely ``min_periods``, ``center``, ``closed`` and
        ``step`` will be passed to ``get_window_bounds``.
    
    min_periods : int, default None
        Minimum number of observations in window required to have a value;
        otherwise, result is ``np.nan``.
    
        For a window that is specified by an offset, ``min_periods`` will default to 1.
    
        For a window that is specified by an integer, ``min_periods`` will default
        to the size of the window.
    
    center : bool, default False
        If False, set the window labels as the right edge of the window index.
    
        If True, set the window labels as the center of the window index.
    
    win_type : str, default None
        If ``None``, all points are evenly weighted.
    
        If a string, it must be a valid `scipy.signal window function
        <https://docs.scipy.org/doc/scipy/reference/signal.windows.html#module-scipy.signal.windows>`__.
    
        Certain Scipy window types require additional parameters to be passed
        in the aggregation function. The additional parameters must match
        the keywords specified in the Scipy window type method signature.
    
    on : str, optional
        For a DataFrame, a column label or Index level on which
        to calculate the rolling window, rather than the DataFrame's index.
    
        Provided integer column is ignored and excluded from result since
        an integer index is not used to calculate the rolling window.
    
    axis : int or str, default 0
        If ``0`` or ``'index'``, roll across the rows.
    
        If ``1`` or ``'columns'``, roll across the columns.
    
        For `Series` this parameter is unused and defaults to 0.
    
    closed : str, default None
        If ``'right'``, the first point in the window is excluded from calculations.
    
        If ``'left'``, the last point in the window is excluded from calculations.
    
        If ``'both'``, the no points in the window are excluded from calculations.
    
        If ``'neither'``, the first and last points in the window are excluded
        from calculations.
    
        Default ``None`` (``'right'``).
    
        .. versionchanged:: 1.2.0
    
            The closed parameter with fixed windows is now supported.
    
    step : int, default None
    
        .. versionadded:: 1.5.0
    
        Evaluate the window at every ``step`` result, equivalent to slicing as
        ``[::step]``. ``window`` must be an integer. Using a step argument other
        than None or 1 will produce a result with a different shape than the input.
    
    method : str {'single', 'table'}, default 'single'
    
        .. versionadded:: 1.3.0
    
        Execute the rolling operation per single column or row (``'single'``)
        or over the entire object (``'table'``).
    
        This argument is only implemented when specifying ``engine='numba'``
        in the method call.
    
    Returns
    -------
    ``Window`` subclass if a ``win_type`` is passed
    
    ``Rolling`` subclass if ``win_type`` is not passed
    """
    pass
```
### Output (GPT-4)
```
window: [1, 5, 10, '3D', '5H']
min_periods: [None, 1, 3, 5]
center: [False, True]
win_type: [None, 'boxcar', 'triang', 'hamming']
on: [None, 'column1', 'column2']
axis: [0, 1, 'index', 'columns']
closed: [None, 'right', 'left', 'both', 'neither']
step: [None, 1, 2, 4]
method: ['single', 'table']
```
