"# nstp_recsys" 


## copy GA training data from google cloud bucket to GCE data/folder
gsutil  cp -r gs://recserve_mp-bigdata/nst/nst.csv  data

## train local and save the result to bucket
export BUCKET="gs://recserve_mp-bigdata/nst"
./mltrain.sh local data/nst.csv  --data-type web_views --use-optimized --output-dir ${BUCKET}
