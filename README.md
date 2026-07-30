import numpy as np

def multiply_matrices_numpy(matrix_a, matrix_b):
    """
    Multiplies two matrices using NumPy.
    Ensures safe shape verification before calculation.
    """
    # Convert lists to NumPy arrays
    array_a = np.array(matrix_a)
    array_b = np.array(matrix_b)
    
    # Check if multiplication is mathematically valid
    if array_a.shape[1] != array_b.shape[0]:
        raise ValueError(
            f"Cannot multiply: Columns of A ({array_a.shape[1]}) must match Rows of B ({array_b.shape[0]})."
        )
        
    # Perform matrix multiplication using the @ operator
    return array_a @ array_b

# Example matrices
matrix_1 = [[1, 2, 3], 
            [4, 5, 6]]

matrix_2 = [[7, 8], 
            [9, 10], 
            [11, 12]]

# Execute and view result
try:
    result = multiply_matrices_numpy(matrix_1, matrix_2)
    print("NumPy Result:")
    print(result)
except ValueError as error:
    print(error)
    
