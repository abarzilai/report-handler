# report-handler

The tool keeps you project envieronment clean by delete or archive files with specified extensions.

Usage:

# Create report handler with logging enable.
rh = ReportHandler(log_enable=True)

# Apply clean policiy on project folder: to delete all files with extentions txt and log.
rh.set_cleaner(folder_path="\working directory",
               age_before_del_hour=0,
               ext_to_del=["log","txt"])

# Apply archive policiy on log folder: to archive all files with extention log.
rh.set_archivator(sourse_folder="\working directory\Logs",
                  archive_folder="\working directory\Logs\Archive",
                  archive_prefix="MyTest",
                  ext_to_arch=["log"],
                  delete_archived_files=True)

# Apply clean policiy on Archive folder: to delete all archives older then 24 hours.
rh.set_cleaner(folder_path="\working directory\Logs\Archive",
               age_before_del_hour=24,
               ext_to_del=["zip"])

# Prints all defined cleaners
rh.show_cleaner()

# Prints all defined archivators
rh.show_archivator()

# Run cleaning
rh.clean()

# Run archivation
rh.archive()

# Run both archive and clean
rh.arcive_and_clean()


