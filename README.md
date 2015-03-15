# SystemBackup
Full unix system backup

Dependancies: rsync

Usage: ./sysbak



- creates /mnt/backups folder if there isn't one and
  either:

	a) mounts specified drive partition to 
	   /mnt/backups as a mountpoint

	or

	b) creates backup on the same drive 
	   /mnt is on

- creates directory /mnt/backups/{date & time}

- backs up root filesystem using:
`	rsync -aAXv --exclude={"/dev/*","/proc/*","/sys/*","/tmp/*","/run/*","/mnt/*","/media/*","/lost+found"} /* /mnt/backups/{date & time}`
