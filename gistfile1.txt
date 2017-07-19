import numpy as np

axis = np.linspace(0.0, 1.0, 11)
log_axis = np.log( axis + 1e-32 )   # smoothing term

print "     y", " ".join( [ "%5.2f" % x for x in axis.tolist()] )
print "-log y", " ".join( [ "%5.2f" % -x for x in log_axis.tolist()] )

print ""
print "Loss = -y*log(y') table"
x_axis = " ".join( [ "%5.2f" % x for x in axis.tolist()] )
print "y\y'", x_axis

for y in range(0, 11, 1):
    line_list = []
    for x in range (0, 11, 1):
        value = -1 * axis[y] * log_axis[x]
        line_list.append( "%5.2f" % value )
        
    print " %.1f" % axis[y], " ".join( line_list )