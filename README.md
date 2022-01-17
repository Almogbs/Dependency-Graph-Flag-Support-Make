# Dependency-Graph-Flag-Support-Make

## Add Support for Dependency-Graph Flag - Make
#### Get Make-4.3 - https://ftp.gnu.org/gnu/make/

### Download:
    git clone https://github.com/Almogbs/Dependency-Graph-Flag-Support-Make.git

### Installation:
    cd Dependency-Graph-Flag-Support-Make
    tar make-4.3.tar.gz
    cd make-4.3
    cp ../. src/
    mkdir build
    cd build
    configure --prefix="$HOME/make/root"
    make
    make install
    make all install
    
### Makefile Example:
    /** Makefile **/
    
    a : b  c
	    touch a
    b: c
	    touch b
    c:
	    touch c

### Usage Example:
    /** Therminal **/
    
    root/bin/make --gen-depgraph=new_file

### Output:
    /** new_file **/
    
    digraph depgraph {
      a -> b;
      a -> c;
      b -> c;
    }

