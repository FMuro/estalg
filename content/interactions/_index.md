+++
title = "Interacciones"
weight = 30
pre = "<i class='fa fa-magic'></i> "
hidden = false
js = ["sagecell"]
+++

Esta página contiene aplicaciones interactivas que nos ayudan a visualizar algunas de las ideas más novedosas que se estudian en la asignatura. Se ejecutan al pulsar el botón **Ejecutar**. 

{{% watch %}}
En ocasiones pueden tardar bastante tiempo en cargarse. Ten paciencia.
{{% /watch %}}

## Divisiones euclídeas en enteros cuadráticos imaginarios

La siguiente aplicación interactiva te permite explorar la posibilidad de realizar divisiones euclídeas respecto del cuadrado del módulo complejo en el anillo de enteros cuadráticos imaginarios $R\subset\mathbb Q[\sqrt{-n}]$ para ciertos valores positivos de $n$. Para $n=1$ tenemos los enteros de Gauss. Puedes seleccionar los coeficientes del dividendo $D=a+b\sqrt{-n}$ y del divisor $d=x+y\sqrt{-n}$, si $-n\not\equiv 1$ mod $4$. Si $-n\equiv 1$ mod $4$, el dividendo y el divisor son de la forma $D=a+b\frac{1+\sqrt{-n}}{2}$ y $d=x+y\frac{1+\sqrt{-n}}{2}$, respectivamente. Los coeficientes del dividendo pueden estar en $[-10,10]$ y los del divisor en $[-5,5]$. Aparece un círculo amarillo centrado en $D$ de radio $|d|$. Los puntos verdes son elementos del anillo y los azules son además múltiplos del divisor. Cada punto azul en el _interior_ del círculo representa una división euclídea. La aplicación da la lista de todos los pares $(c,r)$ que producen divisiones euclídeas $D=d\cdot c+r$.

<div class="sage">
 <script type="text/x-sage">
from sage.plot.circle import Circle
@interact(layout={'top': [['parameter'],['dividend_x', 'divisor_x'],['dividend_y','divisor_y']]})
def _(parameter=selector([1,2,3,5,6,7,10,11], label="n=", buttons=True), dividend_x=slider(-10,10, step_size=1, default = 0, label="a="), dividend_y=slider(-10,10, step_size=1, default = 0, label="b="), divisor_x=slider(-5,5, step_size=1, default = 1, label="x="), divisor_y=slider(-5,5, step_size=1, default = 0, label="y=")):
    if ((divisor_x,divisor_y) == (0,0)):
        show("NO SE PUEDE DIVIDIR POR CERO. ESCOJE UN DIVISOR NO NULO.")
    else:
        if (-parameter % 4 != 1):
            dividend = dividend_x+I*dividend_y*sqrt(parameter)
            divisor = divisor_x+I*divisor_y*sqrt(parameter)
            radius = N(abs(divisor))
            bound_x = floor(radius)+1
            bound_y = floor(radius/sqrt(parameter))+1
            interval_lattice_x = [dividend.real()-bound_x .. dividend.real()+bound_x]
            interval_lattice_y = [dividend.imag()+y*sqrt(parameter) for y in [-bound_y .. bound_y]]
            lattice = cartesian_product([interval_lattice_x,interval_lattice_y]).list()
            multiples = [z for z in lattice if ((((z[0]+I*z[1])/divisor).real()).is_integer() and (((z[0]+I*z[1])/divisor).imag()/sqrt(parameter)).is_integer())]
        else:
            dividend = dividend_x+dividend_y*(1+I*sqrt(parameter))/2
            divisor = divisor_x+divisor_y*(1+I*sqrt(parameter))/2
            radius = N(abs(divisor))
            bound_x = floor(radius)+1
            bound_y = floor(2*radius/sqrt(parameter))+1
            lattice = [(dividend.real()+x+1/2*is_odd(y), dividend.imag()+y*sqrt(parameter)/2) for y in [-bound_y .. bound_y] for x in [-bound_x .. bound_x]]
            def integer_odd(x,y):
                if x.is_integer():
                    return (y+1/2*ZZ(x).mod(2)).is_integer()
                else:
                    return False
            multiples = [z for z in lattice if integer_odd(((z[0]+I*z[1])/divisor).imag()*2/sqrt(parameter),((z[0]+I*z[1])/divisor).real())]
        divisions = [z for z in multiples if abs(divisor)-abs(dividend - (z[0]+I*z[1])) > 0]
        if len(divisions) == 0:
            show("NO HAY DIVISIONES EUCLÍDEAS.")
        else:
            for z in divisions:
                show((expand((z[0]+I*z[1])*divisor.conjugate()/(divisor.real()^2+divisor.imag()^2)), dividend-(z[0]+I*z[1])))
        lattice_plot = point(lattice, rgbcolor='green')
        multiples_plot = point(multiples, rgbcolor='blue', size=50)
        circ = circle((dividend.real(), dividend.imag()), radius, alpha=.4, fill = True, facecolor='yellow', thickness=0)
        if (dividend.real(),dividend.imag()) in multiples:
            cent = point([(dividend.real(),dividend.imag())], rgbcolor='blue', size=200)
        else:
            cent = point([(dividend.real(),dividend.imag())], rgbcolor='green', size=200)
        return show(circ+lattice_plot+multiples_plot+cent, aspect_ratio=1)
 </script>
</div>


## Primos de Gauss

La siguiente aplicación interactiva permite explorar la distribución de los primos de Gauss en cuadrados de diferente tamaño centrados en el origen. Los lados del cuadrado tienen tamaño $2n$. Los puntos rojos son los primos de Gauss de módulo al cuadrado 2. En azul están los que son enteros. El resto, en verde.

<div class="sage">
 <script type="text/x-sage">
@interact
def _(n=slider(3,100, step_size=1, default = 5, label="n=")):
    lattice1 = []
    lattice2 = [[1,1], [1,-1], [-1,1], [-1,-1]]
    lattice3 = []
    for x in [-n .. n]:
        for y in [-n .. n]:
            if is_prime(x^2+y^2) and (x^2+y^2).mod(4) == 1:
                lattice1 = lattice1 + [[x,y]]
    for z in list(primes(3,n+1)):
        lattice3 = lattice3 + [[z,0], [-z,0]]
    lattice1_plot = point(lattice1, rgbcolor='green', size=400/n)
    lattice2_plot = point(lattice2, rgbcolor='red', size=800/n)
    lattice3_plot = point(lattice3, rgbcolor='blue', size=800/n)
    return show(lattice1_plot+lattice2_plot+lattice3_plot, aspect_ratio=1)
 </script>
</div>


## Ternas pitagóricas

La siguiente aplicación muestra los pares $(x,y)$ que forman parte de una terna pitagórica primitiva con $x$ impar y $x,y\leq n$, donde $n$ puede ser cualquier múltiplo de $10$ comprendido entre $10$ y $3000$.

<div class="sage">
 <script type="text/x-sage">
@interact
def _(n=slider(10,3000, step_size=10, default = 100, label="n=")):
    octant = [[a,b] for a in [1..floor(n/2)] for b in [1..(a-1)]]
    parameters = []
    for x in octant:
        if gcd(x[0],x[1]) == 1 and x[0].mod(2) != x[1].mod(2):
            parameters.append(x)
    big_list = [[y[0]^2-y[1]^2,2*y[0]*y[1]] for y in parameters]
    small_list = []
    for z in big_list:
        if z[0] <= n and z[1] <= n and z[0] > 0:
            small_list.append(z)
    return show(point(small_list, rgbcolor='green', size=min(max(30,2*3000/n),100), aspect_ratio=1))
 </script>
</div>


## Forma normal de Smith

La siguiente aplicación es una calculadora de la forma normal de Smith paso a paso. El dato de entrada es una matriz con entradas en $\mathbb{Z}$ expresada como lista de filas.

<div class="sage">
 <script type="text/x-sage">
@interact
def _(A = input_box('[[0,4,6],[5,8,10]]', width = 40, type = matrix, label='Matriz $A=$'), showQ=checkbox(False, label='Calcula $Q$'), showPm=checkbox(False, label='Calcula $P^{-1}$'), auto_update=False):
    def qr(a,b): # euclidean division of a by b with smallest abs(remainder)
        quotient, remainder = a.quo_rem(b)
        if abs(remainder) > abs(b/2): # if the remainder is too big, take the other Euclidean division
            quotient = quotient+sign(b)*sign(remainder)
            remainder = remainder-abs(b)*sign(remainder)
        return [quotient,remainder]
    def smallest(M,l): # find the smallest non-zero element in the bottom right corner starting at (l,l)
        answer = [0] # initialize with trivial answer
        for i in [l .. (M.nrows() - 1)]: # Parse entries
            for j in [l .. (M.ncols() - 1)]:
                if M[i,j] != 0: # check whether entry is non-zero
                    if answer == [0]: # if no non-zero entry had been stored, store this entry
                        answer = [M[i,j],i,j]
                    else: # if some non-zero entry had been stored
                        if abs(M[i,j]) < abs(answer[0]): # check whether the new entry is smaller than the stored value
                            answer = [M[i,j],i,j] # take new entry as new answer
        return answer # it yields the smallest value and its coordinates, or the trivial answer if the submatrix was trivial
    def row_modular(M,l): # find the first element M[l,j] not divisible by M[l,l]
        j = l+1
        while j < M.ncols():
            if M[l,j].mod(M[l,l]) != 0:
                return [M[l,j],j] # return the first one and its column coordinate
            else:
                j = j+1
        return [0] # return this trivial answer if M[l,l] divides all elements to its right
    def nondivisible(M,l): # find in the submatrix below right (l,l) an element which is not divisible by  M[l,l]
        answer = [0] # initialize with trivial answer
        rows = M.nrows() # number of rows
        cols = M.ncols() # number of columns
        i = l # we start checking M[l,l+1]
        j = l+1
        while answer == [0] and i < rows: # we will stop as soon as we find one or we exhaust all entries
            if j < cols: # j is a valid column number
                if M[i,j].mod(M[l,l]) != 0: # check whether entry is not divisible by M[l,l]
                    answer = [M[i,j],i,j] # store entry and coordinates
                else:
                    j = j+1 # next column
            else:
                i = i+1 # next row
                j = l # column l
        return answer # it yields the smallest value and its coordinates, or the trivial answer if the submatrix was trivial
    def format_scalar(r): # display nice multiplying integer
        if r == 1:
            return ' + '
        if r == - 1:
            return ' - '
        if r > 0 and r != 1:
            return ' + '+str(r)
        if r < 0 and r != -1:
            return ' - '+str(-r)
    def type1rows(M,i,j,r): # type 1 row operation with statement (without arrow)
        M.add_multiple_of_row(i,j,r)
        return 'F_{'+str(i+1)+'}'+format_scalar(r)+'F_{'+str(j+1)+'}'
    def type1cols(M,i,j,r): # type 1 column operation with statement (without arrow)
        M.add_multiple_of_column(i,j,r)
        return 'C_{'+str(i+1)+'}'+format_scalar(r)+'C_{'+str(j+1)+'}'
    def type2rows(M,i,j): # type 2 row operation with statement over an arrow
        M.swap_rows(i,j)
        return ' \\stackrel{F_{'+str(i+1)+'} \\leftrightarrow F_{'+str(j+1)+'}}{\\longrightarrow} '
    def type2cols(M,i,j): # type 2 column operation with statement over an arrow
        M.swap_columns(i,j)
        return ' \\stackrel{C_{'+str(i+1)+'} \\leftrightarrow C_{'+str(j+1)+'}}{\\longrightarrow} '
    def smith(M): # compute Smith normal form D and invertible matrices Q and Pm such that Q*M*Pm = D
        Keep = matrix(M) # keep the original argument
        M = matrix(M) # turn M into a matrix in case it where just a list of rows
        d = infinity # initialize smallest non-zero element size with infinity
        i = 0 # start with the whole matrix
        rows = M.nrows() # number of rows
        cols = M.ncols() # number of columns
        Q = identity_matrix(rows) # invertible matrix on the left
        Pm = identity_matrix(cols) # invertible matrix on the right
        L = latex(M) # initialize LaTeX output for algorithm computing D
        LQ = latex(Q) # initialize LaTeX output for algorithm computing Q
        LPm = latex(Pm) # initialize LaTeX output for algorithm computing Pm
        while i < min(rows,cols) and abs(d) > 0: # Row/column where we start operating (the submatrix) 
            small = smallest(M,i) # smallest non-zero element of the submatrix
            d = small[0]
            if d != 0: # check whether the submatrix is non-trivial, and then place the smallest element at (i,i) if non-zero
                if small[1] > i: # the row operation, if necessary
                    L = L + type2rows(M,i,small[1]) + latex(M)
                    LQ = LQ + type2rows(Q,i,small[1]) + latex(Q)
                if small[2] > i: # the column operation, if necessary
                    L = L + type2cols(M,i,small[2]) + latex(M)
                    LPm = LPm + type2cols(Pm,i,small[2]) + latex(Pm)
                nondivrow = row_modular(M,i) # find non-divisible element to the right
                if nondivrow[0] != 0: # column operation for division with remainder, if necessary
                    scalar,d = qr(nondivrow[0],M[i,i]) # the quotient and the remainder, new smallest non-zero element
                    L = L + ' \\stackrel{' + type1cols(M,nondivrow[1],i,-scalar) + '}{\\longrightarrow} ' + latex(M)
                    LPm = LPm + ' \\stackrel{' + type1cols(Pm,nondivrow[1],i,-scalar) + '}{\\longrightarrow} ' + latex(Pm)
                else:
                    nondivcol = row_modular(M.transpose(),i) # find non-divisible element below
                    if nondivcol[0] != 0: # Row operation for division with remainder, if necessary
                        scalar,d = qr(nondivcol[0],M[i,i]) # the quotient and the remainder, new smallest non-zero element
                        L = L + ' \\stackrel{' + type1rows(M,nondivcol[1],i,-scalar) + '}{\\longrightarrow} ' + latex(M)
                        LQ = LQ + ' \\stackrel{' + type1rows(Q,nondivcol[1],i,-scalar) + '}{\\longrightarrow} ' + latex(Q)
                    else: # kill elements to the right and bottom of M[i,i]
                        test = False # >test to check if something (non-zero) will be killed to the right
                        L1 = '' # initialize set of stacked column operations
                        LPm1 = '' # idem
                        for col in [(i+1) .. (cols-1)]: # kill all elements to the right of M[i,i]
                            if M[i,col] != 0:
                                scalar = M[i,col]/M[i,i] # the quotient
                                L1 = L1 + type1cols(M,col,i,-scalar) + ' \\cr '
                                LPm1 = LPm1 + type1cols(Pm,col,i,-scalar) + ' \\cr '
                                test = True # if something has been killed
                        if test: # add new steps if the matrix has been modified
                            L = L + ' \\stackrel{\\substack{' + L1 + '}}{\\longrightarrow} ' + latex(M)
                            LPm = LPm + ' \\stackrel{\\substack{' + LPm1 + '}}{\\longrightarrow} ' + latex(Pm)
                        test = False # test to check if something (non-zero) will be killed at the bottom
                        L2 = '' # initialize set of stacked row operations
                        LQ2 = '' # idem
                        for row in [(i+1) .. (rows-1)]: # kill all elements below M[i,i]
                            if M[row,i] != 0:
                                scalar = M[row,i]/M[i,i] # the quotient
                                L2 = L2 + type1rows(M,row,i,-scalar) + ' \\cr '
                                LQ2 = LQ2 + type1rows(Q,row,i,-scalar) + ' \\cr '
                                test = True # if something has been killed
                        if test: # add new steps if the matrix has been modified
                            L = L + ' \\stackrel{\\substack{' + L2 + '}}{\\longrightarrow} ' + latex(M)
                            LQ = LQ + ' \\stackrel{\\substack{' + LQ2 + '}}{\\longrightarrow} ' + latex(Q)
                        nondiv = nondivisible(M,i) # find in the submatrix below right (i,i) an element which is not divisible by  M[i,i]
                        if nondiv[0] != 0: # if it exists...
                            L = L + ' \\stackrel{' + type1rows(M,i,nondiv[1],1) + '}{\\longrightarrow} ' + latex(M) # perform a row operation to fuck up row i
                            LQ = LQ + ' \\stackrel{' + type1rows(Q,i,nondiv[1],1) + '}{\\longrightarrow} ' + latex(Q)  
                        else:
                            i = i+1
        show(html('Este programa, apartir de una matriz de enteros $A$ introducida como lista de filas, calcula paso a paso su forma normal de Smith $D$ y matrices invertibles $Q$ y $P^{-1}$ tales que $QAP^{-1}=D$.'))
        show(html('C&aacute;lculo de $D$:'))
        show('A='+latex(L)+'=D')
        if showQ:
            show(html('C&aacute;lculo de $Q$:'))
            show('I='+latex(LQ)+'=Q')
        if showPm:
            show(html('C&aacute;lculo de $P^{-1}$:'))
            show('I='+latex(LPm)+'=P^{-1}')
        if Q*Keep*Pm != M: # perform a test
            show('LOS RESULTADOS SON ERRÓNEOS')
        return (M, Q, Pm) # it gives the Smith normal form and two invertible matrices Q and Pm such that Q*M*Pm is the Smith normal form
    smith(A)
</script>
</div>
