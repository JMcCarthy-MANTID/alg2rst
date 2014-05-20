.. algorithm:: Linear

.. summary:: Linear

.. aliases:: Linear

.. usage:: Linear

.. properties:: Linear

This algorithm fits a line, of the form :math:`Y = c0 + c1 X`, to the
specified part of a particular spectrum. As well as outputting the
result to the log (debug level) and as output properties, a 1D workspace
is created with the same X bins/points as the fitted spectrum and the
value and error on the fit at each point. The covariance matrix is not
currently returned as an output: if this is required please contact the
development team.

References
^^^^^^^^^^

This algorithm uses the gsl linear regression algorithms
*gsl\_fit\_linear* and *gsl\_fit\_wlinear*, which are documented
`here <http://www.gnu.org/software/gsl/manual/html_node/Linear-regression.html>`__.

.. categories:: Linear