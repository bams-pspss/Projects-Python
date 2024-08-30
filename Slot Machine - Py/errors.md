# Error or Warning Approach

1. TypeError: 'NoneType' object is not subscriptable
    - Attempt to access an index or a key of a variable that is of the NoneType data type. <br>
    This error usually occurs when a method or a function returns None rather than the desired value
`CODE:`
`
def get_slot_machine_spin(rows, cols, symbols):
    all_symbols = []
    for symbol, symbol_count in symbols.items():
        for _ in range(symbol_count):
            all_symbols.append(symbol)
    columns = []
    for _ in range(cols):
        column = []
        current_symbol = all_symbols[:]

        for _ in range(rows):
            value = random.choice(all_symbols)
            current_symbol.remove(value)
            column.append(value)

        columns.append(column)
`
`Error:`
`
line 46, in print_slot_machine
    for row in range(len(columns[0])):
                         ~~~~~~~^^^
TypeError: 'NoneType' object is not subscriptable
`

 * **What happen:** Forget to put return columns
 * **Solution:** return columns