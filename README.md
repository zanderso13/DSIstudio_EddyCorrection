# DSIstudio_EddyCorrection

To run a single subject/test the scripts you can run something like the following (assuming you're in the respository directory)

./single_sub_dti_preproc.sh sub-MWMH001

The script works by going to the subject directory, makes a folder, renames some files to work well with FSL, and then runs bet2 and the eddy function. The index.txt and acpq.txt files will always be the same across subjects, but eddy breaks if they're not in the same folder as the images.

To run a batch job:

./preproc_data.sh sub.txt


The subs.txt file contains subject folders for all MWMH subjects. You can (and maybe should) do small chunks of this list. I've had issues where Quest errors out on particular subjects when you submit too many jobs to the cluster all at once. I'm not sure why this happens but submitting in groups of 20ish should be good


I haven't finished an entire run of this script so I'm not sure how long it takes. I've included a line at the beginning and end of the script that output the time and date at the beginning and end. This will hopefully tell us how much time is actually needed to run each script.

I've set the time up in quest to go for 4 hrs on the short partition. Fingers crossed it's enough!
