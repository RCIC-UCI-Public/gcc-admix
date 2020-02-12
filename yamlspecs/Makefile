# Copyright (c) 2000 - 2019 The Regents of the University of California.
# All rights reserved.	
# This includes the Generic yaml2rpm Makefile - most packaging should
# be able to use this.
SUBMAKES = Makefile6 Makefile8
.DEFAULT_GOAL = default
%.pkg:
	for f in $(SUBMAKES); do \
		if [ -f $@ ] ; then /bin/rm $@; fi; \
		$(MAKE) -f $$f $@; \
        done
	
ansible: 
	$(MAKE) -s -f Makefile6 $@ 

manifest module-provides module-requires:
	$(MAKE) -s -f Makefile6 $@ 
	$(MAKE) -s -f Makefile8 $@ 
%: 	
	$(MAKE) -f Makefile6 $*
	$(MAKE) -f Makefile6 clean
	$(MAKE) -f Makefile8 $*
	
	
