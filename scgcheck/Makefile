#ident @(#)Makefile	1.12 09/01/14 
###########################################################################
SRCROOT=	..
RULESDIR=	RULES
include		$(SRCROOT)/$(RULESDIR)/rules.top
###########################################################################

INSDIR=		bin
TARGET=		scgcheck
CPPOPTS +=	-I../libscg
CPPOPTS +=	-I../cdrecord
CPPOPTS +=	-DSCHILY_PRINT

CFILES=		scgcheck.c sense.c dmaresid.c \
		scsi_scan.c scsi_cdr.c cd_misc.c

HFILES=		scgcheck.h version.h
#LIBS=		-lschily $(LIB_SOCKET)
LIBS=		-lscgcmd -lrscg -lscg $(LIB_VOLMGT) -lschily $(SCSILIB) $(LIB_SOCKET)
XMK_FILE=	Makefile.man

scsi_scan.c scsi_cdr.c cd_misc.c:
	@echo "	==> MAKING SYMLINKS in ." && sh ./MKLINKS
$(ALLTARGETS): scsi_scan.c scsi_cdr.c

###########################################################################
include		$(SRCROOT)/$(RULESDIR)/rules.cmd
###########################################################################
count:	$(CFILES) $(HFILES)
	count $r1
