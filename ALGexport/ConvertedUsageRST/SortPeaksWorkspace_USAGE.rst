The following show some python usage examples.

1. Sorting to form a newly sorted copy of the input workspace.

``sorted_workspace = SortPeaksWorkspace(InputWorkspace=workspace_to_sort, ColumnNameToSortBy='k')``

2. Sorting performed in-place.

``workspace_to_sort_inplace = SortPeaksWorkspace(InputWorkspace = workspace_to_sort_inplace, ColumnNameToSortBy='l')``
