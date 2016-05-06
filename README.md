# sam2BigWig

This script will take a sam file **mapped to the human genome hg19** and convert it to a bigwig file that could be loaded to UCSC Genome Browser. It depends on samtools, then bedtools bamtobed (aka bamToBed), and it will attempt to download and execute three UCSC scripts, bedItemOverlapCount, bedGraphToBigWig and fetchChromSizes, so make sure your connection is working.

# Usage

<pre>
chmod 775 sam2bigwig
./sam2bigwig file.sam
</pre>

Note the sam file name is an example, add your file name.

# Example output

<pre>
./sam2BigWig.sh Aligned.out.sam

--2016-05-04 13:43:38--  http://hgdownload.soe.ucsc.edu/admin/exe/linux.x86_64/bedItemOverlapCount
Resolving hgdownload.soe.ucsc.edu (hgdownload.soe.ucsc.edu)... 128.114.119.163
Connecting to hgdownload.soe.ucsc.edu (hgdownload.soe.ucsc.edu)|128.114.119.163|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15594359 (15M) [text/plain]
Saving to: ‘bedItemOverlapCount’

100%[=======================================================================================================================================================>] 15,594,359  35.1MB/s   in 0.4s 

2016-05-04 13:43:39 (35.1 MB/s) - ‘bedItemOverlapCount’ saved [15594359/15594359]

--2016-05-04 13:43:39--  http://hgdownload.soe.ucsc.edu/admin/exe/linux.x86_64/fetchChromSizes
Resolving hgdownload.soe.ucsc.edu (hgdownload.soe.ucsc.edu)... 128.114.119.163
Connecting to hgdownload.soe.ucsc.edu (hgdownload.soe.ucsc.edu)|128.114.119.163|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2793 (2.7K) [text/plain]
Saving to: ‘fetchChromSizes’

100%[=======================================================================================================================================================>] 2,793       --.-K/s   in 0s

2016-05-04 13:43:39 (119 MB/s) - ‘fetchChromSizes’ saved [2793/2793]

INFO: trying WGET /usr/bin/wget for database hg19
url: http://hgdownload.cse.ucsc.edu/goldenPath/hg19/bigZips/hg19.chrom.sizes
--2016-05-04 14:48:49--  http://hgdownload.soe.ucsc.edu/admin/exe/linux.x86_64/bedGraphToBigWig
Resolving hgdownload.soe.ucsc.edu (hgdownload.soe.ucsc.edu)... 128.114.119.163
Connecting to hgdownload.soe.ucsc.edu (hgdownload.soe.ucsc.edu)|128.114.119.163|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3831823 (3.7M) [text/plain]
Saving to: ‘bedGraphToBigWig’

100%[=======================================================================================================================================================>] 3,831,823   --.-K/s   in 0.1s  

2016-05-04 14:48:49 (33.6 MB/s) - ‘bedGraphToBigWig’ saved [3831823/3831823]

</pre>
