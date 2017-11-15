from building import *

cwd     = GetCurrentDir()

src     = []
CPPPATH = [cwd]

LIBS    = []
LIBPATH = []

if GetDepend('SOC_FH8620'):
    LIBS = ['wlan-wiced_gcc_fh8620']
    LIBPATH = [cwd + '/fh8620']
    
elif GetDepend('BOARD_X1000_REALBOARD'):
    LIBPATH = [cwd + '/x1000']

    if GetDepend('RT_USING_HARD_FLOAT'):
        LIBS = ['wlan-wiced_gcc_x1000_fpu.a']        
    else:
        LIBS = ['wlan-wiced_gcc_x1000.a']

group = DefineGroup('wlan-wiced', src, depend = ['PKG_USING_WLAN_WICED', 'RT_USING_LWIP'], CPPPATH = CPPPATH, LIBS = LIBS, LIBPATH = LIBPATH)

Return('group')
