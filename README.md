# TRR289 A02 (akpla )

## ℹ️ Information
*This repository is the Github sibling of the corresponding [DataLad](https://www.datalad.org/) dataset, i.e. it **does not** contain the data itself.*
The GitHub sibling, nevertheless, provides insights into the general data structure (directory tree, filenames) and serves as a starting point to download, share and discuss the dataset.
 Data is in BIDS format and may include behavioral, questionnaire and derivative data, too.
Data is stored in a special S3 remote provided by [Coscine](https://coscine.rwth-aachen.de/) and can't be downloaded without the dataset specific secret token.
Token is available at project Z03 for members of TRR289 and collaborators upon reasonable request.

See `dataset_description.json` for project related meta-data.

## ⬇️ How to download dataset

#### 1. Install it with DataLad based on the github handle
This does not download the actual data, only the gin-annex "skeleton".
```bash
datalad install -s git@github.com:pni-data/<dataset_name>.git <dataset_name>
```
#### 2. Set up the security token to access the actual data
Token is available at project Z03 for members of TRR289 and collaborators upon reasonable request.
```bash
export AWS_ACCESS_KEY_ID="XXXXX-XXXX-XXXX-XXXX-XXXX"
export AWS_SECRET_ACCESS_KEY="XXXXXXXX"
```

#### 2. Change to the dataset directory and download the file(s) you want
You can selectively download what you need (e.g. derivatives only).
```bash
cd <dataset_name>
datalad get <path/to/file*>
```


See our [documentation](https://github.com/pni-data/.github/blob/master/profile/README.md) for more detail.

Comments added by the SFB289 Z03 project coordinators
====================================================================

General Comments
--------------------------------------------------------------------
ToDo:

description of the dataset,including link to the openly available SFB proposal/some publication
eg: This dataset was acquired by the team of the SFB289 XX project. It includes YY subjects and the common sequences within the SFB289 project, namely a high resolution T1w, resting state fMRI, 133 direction multi shell DWI, and 2 fieldmaps for the functional data (one reversed phase encoding direction, one Siemens deafult fieldmap sequnce) and one fieldmap for the DWI (reversed field encoding direction). An additional reference image of the resting state fMRI is included without multiband factor.

Questionnaires data are also acquired and can be found in the ... fodler.

The proposal can be found here: link

The BIDS conversion was done with heudiconv by the A02 project coordinators and supported by the Z03 project coordinators.

Defacing
--------------------------------------------------------------------
Defacing was done by the project cooridnator.
SPM was used on all anatomical images to ensure deindentification of subjects. 


Known Issues
--------------------------------------------------------------------
N/A ToDo

--------------------------------------------------------------------


bids-validator@1.13.1
	[33m1: [WARN] Not all subjects contain the same files. Each subject should contain the same number of files with the same naming unless some files are known to be missing. (code: 38 - INCONSISTENT_SUBJECTS)[39m
		./sub-22naw4g1d/fmap/sub-22naw4g1d_acq-bold_dir-PA_run-02_epi.json
			Evidence: Subject: sub-22naw4g1d; Missing file: sub-22naw4g1d_acq-bold_dir-PA_run-02_epi.json
		./sub-22naw4g1d/fmap/sub-22naw4g1d_acq-bold_dir-PA_run-02_epi.nii.gz
			Evidence: Subject: sub-22naw4g1d; Missing file: sub-22naw4g1d_acq-bold_dir-PA_run-02_epi.nii.gz
		./sub-22naw4g1d/func/sub-22naw4g1d_task-rest_run-02_bold.json
			Evidence: Subject: sub-22naw4g1d; Missing file: sub-22naw4g1d_task-rest_run-02_bold.json
		./sub-22naw4g1d/func/sub-22naw4g1d_task-rest_run-02_bold.nii.gz
			Evidence: Subject: sub-22naw4g1d; Missing file: sub-22naw4g1d_task-rest_run-02_bold.nii.gz
		./sub-22r2t4kxt/fmap/sub-22r2t4kxt_acq-bold_dir-PA_run-02_epi.json
			Evidence: Subject: sub-22r2t4kxt; Missing file: sub-22r2t4kxt_acq-bold_dir-PA_run-02_epi.json
		./sub-22r2t4kxt/fmap/sub-22r2t4kxt_acq-bold_dir-PA_run-02_epi.nii.gz
			Evidence: Subject: sub-22r2t4kxt; Missing file: sub-22r2t4kxt_acq-bold_dir-PA_run-02_epi.nii.gz
		./sub-22r2t4kxt/func/sub-22r2t4kxt_task-rest_run-02_bold.json
			Evidence: Subject: sub-22r2t4kxt; Missing file: sub-22r2t4kxt_task-rest_run-02_bold.json
		./sub-22r2t4kxt/func/sub-22r2t4kxt_task-rest_run-02_bold.nii.gz
			Evidence: Subject: sub-22r2t4kxt; Missing file: sub-22r2t4kxt_task-rest_run-02_bold.nii.gz
		./sub-22r6zerzs/fmap/sub-22r6zerzs_acq-bold_dir-PA_run-02_epi.json
			Evidence: Subject: sub-22r6zerzs; Missing file: sub-22r6zerzs_acq-bold_dir-PA_run-02_epi.json
		./sub-22r6zerzs/fmap/sub-22r6zerzs_acq-bold_dir-PA_run-02_epi.nii.gz
			Evidence: Subject: sub-22r6zerzs; Missing file: sub-22r6zerzs_acq-bold_dir-PA_run-02_epi.nii.gz
		[33m... and 306 more files having this issue (Use --verbose to see them all).[39m

[36m	Please visit https://neurostars.org/search?q=INCONSISTENT_SUBJECTS for existing conversations about this issue.[39m

	[33m2: [WARN] Not all subjects/sessions/runs have the same scanning parameters. (code: 39 - INCONSISTENT_PARAMETERS)[39m
		./sub-2m48n76xf/func/sub-2m48n76xf_task-rest_run-01_bold.nii.gz
		./sub-2uh8ja94t/func/sub-2uh8ja94t_task-rest_run-01_bold.nii.gz

[36m	Please visit https://neurostars.org/search?q=INCONSISTENT_PARAMETERS for existing conversations about this issue.[39m

        [34m[4mSummary:[24m[39m                   [34m[4mAvailable Tasks:[24m[39m                     [34m[4mAvailable Modalities:[39m[24m 
        1691 Files, 20.21GB        rest                                 MRI                   
        80 - Subjects              TODO: full task name for rest                              
        1 - Session                                                                           


[36m	If you have any questions, please post on https://neurostars.org/tags/bids.[39m
