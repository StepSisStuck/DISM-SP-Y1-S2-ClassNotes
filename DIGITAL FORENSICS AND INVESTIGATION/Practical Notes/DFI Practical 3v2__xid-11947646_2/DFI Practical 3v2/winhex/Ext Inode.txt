template "Ext2/Ext3 Inode"

// By Jens Kirschner

description "Contains a file's meta information (for Inode size 128 bytes)"
applies_to disk
multiple

begin

	section "File mode"

		octal uint_flex "8,7,6,5,4,3,2,1,0" "Permissions"

		move -4
		uint_flex "15,14,13,12" "File type (8=reg.file, 4=dir.)"

		move -4
		uint_flex "9" "Sticky bit"
	
		move -4
		uint_flex "10" "SGID"

		move -4
		uint_flex "11" "SUID"

		move -2
	endsection

	uint16	"Owner uid"
	uint32	"Size in bytes (low 4 bytes)"
	UNIXDateTime	"Access time"
	UNIXDateTime	"Inode change"
	UNIXDateTime	"Modification"
	UNIXDateTime	"Deletion"
	uint16	"Group id"
	uint16	"Hard link count"
	uint32	"Sector count"
	uint32	"File flags"
	uint32	"OS dependent"
	numbering 1
	{
		uint32	"Direct block #~"
	} [12]
	uint32	"Indirect block"
	uint32	"Double indirect block"
	uint32	"Triple indirect block"
	uint32	"File version"
	uint32	"File ACL"
	uint32	"Size in bytes (high 4 bytes)"
	uint32	"Fragment address"
	uint8		"Fragment #"
	uint8		"Fragment size"
	uint16	"Padding"
	hex 4		"Reserved"
	goto 0
	move 128 // Change this for a different Inode size (128: default)
end