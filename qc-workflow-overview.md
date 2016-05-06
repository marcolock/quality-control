# DAP QC Workflow
|Step #|Phase|File Location|Activity|Tool|Notes|
| ---- |:---:|:-----------:|:------:|:---:|:---:|
|QC-001|Receive harddrive from vendor|Vendor harddrive|	Make sure both the harddrive and the box are labeled with content, vendor, and date information.| |Confirm that what was expected from the vendor was received.|		
|QC-002|Receive harddrive from vendor|Vendor harddrive|	Verify content on the drive matches what the vendor was supposed to send.| |Refer to the Statement of Work and existing project management documents.|		
|QC-003|Receive harddrive from vendor|Vendor harddrive|	Confirm with vendor that the harrdrive was safely received. If there are missing files on the harddrive, notify the vendor in writing immediately.| ||			
|QC-004|Integrity checking|Vendor harddrive|Generate CHECKSUM A on all files on harrdrive|[md5Scrape.py](https://github.com/CarnegieHall/quality-control/blob/master/md5Scrape.py)|All the checksum generated should be stored in a csv. file|			
|QC-005|Basic QC|Vendor harddrive|Perform aural and visual QC review on selected files (25% - beginning, middle, and end of file)||Identify and flag issues for review.|
|QC-006|Metadata QC|Vendor harddrive|Audit the technical metadata against requested  specifications.|[MDQC](https://github.com/avpreserve/mdqc)||		
|QC-007|Transfer|Vendor harddrive|Transfer files from harddrive to Server| | |
|QC-008|Integrity checking|Server|Generate CHECKSUM B on all transferred files on Server|[md5Scrape.py](https://github.com/CarnegieHall/quality-control/blob/master/md5Scrape.py)||	
|QC-009|Integrity checking|Server|Run the script that compares CHECKSUM A (from the harddrive) with CHECKSUM B (on the server) (Server)|[checksumValidation.py](https://github.com/CarnegieHall/quality-control/blob/master/checksumValidation.py)|	|	
|QC-010|Filename audit/metadata matching|Server|Run the script which associates filenames with performance metadata. This script also identifies unmatched event IDs to be cross-checked to ensure no content are missing from the digitized material. Filenames are modified. Does not apply to those files that are not related to events.|[reconcileList.py](https://github.com/CarnegieHall/quality-control/blob/master/reconcileList.py)| |	
|QC-011|Embed metadata|Server|Embed selected metadata field values into audio, video, still images|[embedCopyrightMetadata.sh](https://github.com/CarnegieHall/quality-control/blob/master/embedCopyrightMetadata.sh)||			
|QC-012|DAMS ingest prep|Server|Create metadata CSV for DAMS ingest template| | |		
|QC-013|DAMS ingest prep|Server|Copy to the destination folder and collapse harddrive-dictated hierarchy| | |			