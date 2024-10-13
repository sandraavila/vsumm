# VSUMM (Video SUMMarization)

This repository contains the data (datasets, video/user summaries, CUS evaluation) in the paper [VSUMM: A mechanism designed to produce static video summaries and a novel evaluation method](https://www.sciencedirect.com/science/article/abs/pii/S0167865510002783?via%3Dihub). We originally created the repository in 2011 at (inactive) Google sites [https://sites.google.com/site/vsummsite/](https://sites.google.com/site/vsummsite/download).

Video summarization is one of the most important topics, potentially enabling faster browsing of large video collections and more efficient content indexing and access. Essentially, this research area consists of automatically generating a short summary of a video, which can either be static or dynamic. Static video summaries are composed of a set of keyframes extracted from the original video, while dynamic video summaries are composed of a set of shots and are produced taking into account the similarity or domain-specific relationships among all video shots.

In this project, we developed VSUMM, a methodology for producing static video summaries. The method is based on color feature extraction from video frames and a k-means clustering algorithm. We also developed a novel approach for evaluating video static summaries. In such an approach, several users manually create video summaries, which are then compared both to our approach and to a number of different techniques in the literature.

The main contributions of this paper are:
1. **A mechanism designed to produce static video summaries**, which presents the advantages of the main concepts of related work in the video summarization;
2. **A new evaluation method of video summaries**, which reduces the subjectivity in the evaluation task, quantifies the summary quality, and allows more objective comparisons among different techniques; and
3. **A statistically well-founded experimental evaluation** of both the proposed summarization technique – contrasted to others in the literature – and the evaluation method.

# Datasets & Summaries
**You can download the data in a [single](https://www.dropbox.com/s/79vzkk9z5r9oxj3/VSUMM.zip) or each zip file.**

File (zip) | Size (MB) | Description
:------------ | :------------- | :------------- 
[Dataset](https://www.dropbox.com/s/g0e64b4qfnuual1/database.zip) | 763 | 50 videos from [Open Video](http://www.open-video.org). All videos are in MPEG-1 format (30 fps, 352 x 240 pixels), in color and with sound. These videos are distributed among several genres (documentary, educational, ephemeral, historical, lecture) and their duration varies from 1 to 4 minutes and approximately 75 minutes of video in total.
[User summary](https://www.dropbox.com/s/ilt1jpclzs2o18v/UserSummary.zip) | 31.5 | 250 user summaries. These summaries were created manually by 50 users, each one dealing with 5 videos, meaning that each video has 5 video summaries created by 5 different users.
[VSUMM<sub>1</sub> summary](https://www.dropbox.com/s/47rxdjw34r8dav6/VSUMM1Summary.zip) | 6.28 | 50 video summaries (ours).
[VSUMM<sub>2</sub> summary](https://www.dropbox.com/s/rxuzmg75qvgmy20/VSUMM2Summary.zi) | 4.91 | 50 video summaries (ours).
[OV summary](https://www.dropbox.com/s/2lyz13xdq0ru798/OVSummary.zip) | 6.30 | 50 video summaries (dataset providers). 
[DT summary](https://www.dropbox.com/s/mj3qsvmj7vykx7n/DTSummary.zip) | 3.68 | 50 video summaries [[Mundur et al., 2006]](http://dx.doi.org/10.1007/s00799-005-0129-9).
[STIMO summary](https://www.dropbox.com/s/lt5tuh9xejp7wm2/STIMOSummary.zip) (extended version of [VISTO approach](http://doi.acm.org/10.1145/1282280.1282370)). | 5.86 | 50 video summaries [[Furini et al., 2010]](http://portal.acm.org/citation.cfm?id=1713242).

File (zip) | Size (MB) | Description
:------------ | :------------- | :------------- 
[Dataset](https://www.dropbox.com/s/wxpj91cm9m3ikn0/newDatabase.zip) | 468 | 50 video from websites like YouTube. These videos are distributed among several genres (cartoons, news, sports, commercials, tv-shows and home videos) and their duration varies from 1 to 10 minutes.
[User summary](https://www.dropbox.com/s/7rtbyeo64hk8ot7/newUserSummary.zip) | 45.3 | 250 user summaries. These summaries were created manually by 50 users, each one dealing with 5 videos, meaning that each video has 5 video summaries created by 5 different users.
[VSUMM summary](https://www.dropbox.com/s/2f448wsndg2877r/VSUMMSummary.zip) | 7.93 | 50 video summaries (ours).

# Comparison of User Summaries (CUS) 
CUS evaluation method ([jar](https://github.com/sandraavila/vsumm/blob/main/CUS/CUS.jar), [example](https://github.com/sandraavila/vsumm/blob/main/CUS/CUS.zip)) (update on February 2014). The jai_core and jai_codec were included in the CUS implementation.

Usage:
```
java -jar CUS.jar -i [input_file.txt] -o [output_file.txt] -u [number_user_summaries] -a [number_approaches] -t [threshold (default: 0.5)]
```

* `-i [input_file.txt]`: The first line contains the video directory name. The following lines contain the directory of each user summary and the summaries of each approach. A blank line separates the videos. Input file format:
```
[path]/[video1_name]/
[path]/[video1_name]/[user_summary1]/
[path]/[video1_name]/[user_summary2]/
[path]/[video1_name]/[user_summary3]/
[path]/[video1_name]/[user_summary4]/
[path]/[video1_name]/[user_summary5]/
[path]/[video1_name]/[approach1]/
[path]/[video1_name]/[approach2]/
[path]/[video2_name]/
[path]/[video2_name]/[user_summary1]/
[path]/[video2_name]/[user_summary2]/
[path]/[video2_name]/[user_summary3]/
[path]/[video2_name]/[user_summary4]/
[path]/[video2_name]/[user_summary5]/
[path]/[video2_name]/[approach1]/
[path]/[video2_name]/[approach2]/
```

* `-u [number_user_summaries]`: The number of user summaries for each video.
* `-a [number_approaches]`: The number of approaches which produced the automatic summaries.
* `-t [threshold (default: 0.5)]`: The CUS evaluation method compares each user summary directly with the automatic summaries. The color histogram is applied to compare keyframes from different summaries, and the distance between them is measured using the Manhattan distance. Two keyframes are similar if the distance between them is less than a predetermined threshold. Once two frames are matched, they are removed from the next iteration of the comparing procedure. The default value is 0.5.

# Results

Video | Name | #Frames | Duration | Summary
:------------ | :------------- | :------------- | :------------- | :------------- 
[v21](http://www.open-video.org/details.php?videoid=614) | The Great Web of Water, segment 01 | 3,279 | 1:50 | [v21](https://github.com/sandraavila/vsumm/blob/main/Results/video21.pdf)
[v22](http://www.open-video.org/details.php?videoid=615) | The Great Web of Water, segment 02 | 2,118 | 1:11 | [v22](https://github.com/sandraavila/vsumm/blob/main/Results/video22.pdf)
[v23](http://www.open-video.org/details.php?videoid=670) | The Great Web of Water, segment 07 | 1,745 | 0:59 | [v23](https://github.com/sandraavila/vsumm/blob/main/Results/video23.pdf)
[v24](http://www.open-video.org/details.php?videoid=684) | A New Horizon, segment 01 | 1,806 | 1:01 | [v24](https://github.com/sandraavila/vsumm/blob/main/Results/video24.pdf)
[v25](http://www.open-video.org/details.php?videoid=685) | A New Horizon, segment 02 | 1,797 | 1:00 | [v25](https://github.com/sandraavila/vsumm/blob/main/Results/video25.pdf)
[v26](http://www.open-video.org/details.php?videoid=686) | A New Horizon, segment 03 | 6,249 | 3:29 | [v26](https://github.com/sandraavila/vsumm/blob/main/Results/video26.pdf)
[v27](http://www.open-video.org/details.php?videoid=687) | A New Horizon, segment 04 | 3,192 | 1:47 | [v27](https://github.com/sandraavila/vsumm/blob/main/Results/video27.pdf)
[v28](http://www.open-video.org/details.php?videoid=689) | A New Horizon, segment 05 | 3,561 | 1:59 | [v28](https://github.com/sandraavila/vsumm/blob/main/Results/video28.pdf)
[v29](http://www.open-video.org/details.php?videoid=690) | A New Horizon, segment 06 | 1,944 | 1:05 | [v29](https://github.com/sandraavila/vsumm/blob/main/Results/video29.pdf)
[v30](http://www.open-video.org/details.php?videoid=661) | A New Horizon, segment 08 | 1,815 | 1:01 | [v30](https://github.com/sandraavila/vsumm/blob/main/Results/video30.pdf)
[v31](http://www.open-video.org/details.php?videoid=663) | A New Horizon, segment 10 | 2,517 | 1:24 | [v31](https://github.com/sandraavila/vsumm/blob/main/Results/video31.pdf)
[v32](http://www.open-video.org/details.php?videoid=635) | Take Pride in America, segment 01 | 2,691 | 1:30 | [v32](https://github.com/sandraavila/vsumm/blob/main/Results/video32.pdf)
[v33](http://www.open-video.org/details.php?videoid=637) | Take Pride in America, segment 03 | 3,261 | 1:49 | [v33](https://github.com/sandraavila/vsumm/blob/main/Results/video33.pdf)
[v34](http://www.open-video.org/details.php?videoid=4586) | Digital Jewelry: Wearable Technology for Every Day Life | 4,204 | 3:00 | [v34](https://github.com/sandraavila/vsumm/blob/main/Results/video34.pdf)
[v35](http://www.open-video.org/details.php?videoid=4923) | HCIL Symposium 2002 - Introduction, segment 01 | 2,336 | 1:18 | [v35](https://github.com/sandraavila/vsumm/blob/main/Results/video35.pdf)
[v36](http://www.open-video.org/details.php?videoid=422) | Senses And Sensitivity, Introduction to Lecture 1 presenter | 4,221 | 2:20 | [v36](https://github.com/sandraavila/vsumm/blob/main/Results/video36.pdf)
[v37](http://www.open-video.org/details.php?videoid=425) | Senses And Sensitivity, Introduction to Lecture 2 | 3,411 | 1:53 | [v37](https://github.com/sandraavila/vsumm/blob/main/Results/video37.pdf)
[v38](http://www.open-video.org/details.php?videoid=430) | Senses And Sensitivity, Introduction to Lecture 3 presenter | 4,566 | 2:32 | [v38](https://github.com/sandraavila/vsumm/blob/main/Results/video38.pdf)
[v39](http://www.open-video.org/details.php?videoid=538) | Senses And Sensitivity, Introduction to Lecture 4 presenter | 5,249 | 2:55 | [v39](https://github.com/sandraavila/vsumm/blob/main/Results/video39.pdf)
[v40](http://www.open-video.org/details.php?videoid=719) | Exotic Terrane, segment 01 | 2,940 | 1:38 | [v40](https://github.com/sandraavila/vsumm/blob/main/Results/video40.pdf)
[v41](http://www.open-video.org/details.php?videoid=720) | Exotic Terrane, segment 02 | 2,776 | 1:32 | [v41](https://github.com/sandraavila/vsumm/blob/main/Results/video41.pdf)
[v42](http://www.open-video.org/details.php?videoid=721) | Exotic Terrane, segment 03 | 2,676 | 1:29 | [v42](https://github.com/sandraavila/vsumm/blob/main/Results/video42.pdf)
[v43](http://www.open-video.org/details.php?videoid=722) | Exotic Terrane, segment 04 | 4,797 | 2:40 | [v43](https://github.com/sandraavila/vsumm/blob/main/Results/video43.pdf)
[v44](http://www.open-video.org/details.php?videoid=724) | Exotic Terrane, segment 06 | 2,425 | 1:21 | [v44](https://github.com/sandraavila/vsumm/blob/main/Results/video44.pdf)
[v45](http://www.open-video.org/details.php?videoid=726) | Exotic Terrane, segment 08 | 2,428 | 1:40 | [v45](https://github.com/sandraavila/vsumm/blob/main/Results/video45.pdf)
[v46](http://www.open-video.org/details.php?videoid=731) | America's New Frontier, segment 01 | 3,591 | 1:59 | [v46](https://github.com/sandraavila/vsumm/blob/main/Results/video46.pdf)
[v47](http://www.open-video.org/details.php?videoid=733) | America's New Frontier, segment 03 | 2,166 | 1:12 | [v47](https://github.com/sandraavila/vsumm/blob/main/Results/video47.pdf)
[v48](http://www.open-video.org/details.php?videoid=734) | America's New Frontier, segment 04 | 3,705 | 2:03 | [v48](https://github.com/sandraavila/vsumm/blob/main/Results/video48.pdf)
[v49](http://www.open-video.org/details.php?videoid=737) | America's New Frontier, segment 07 | 3,615 | 2:00 | [v49](https://github.com/sandraavila/vsumm/blob/main/Results/video49.pdf)
[v50](http://www.open-video.org/details.php?videoid=740) | America's New Frontier, segment 10 | 4,830 | 2:41 | [v50](https://github.com/sandraavila/vsumm/blob/main/Results/video50.pdf)
[v51](http://www.open-video.org/details.php?videoid=744) | The Future of Energy Gases, segment 03 | 2,934 | 1:37 | [v51](https://github.com/sandraavila/vsumm/blob/main/Results/video51.pdf)
[v52](http://www.open-video.org/details.php?videoid=746) | The Future of Energy Gases, segment 05 | 3,615 | 2:00 | [v52](https://github.com/sandraavila/vsumm/blob/main/Results/video52.pdf)
[v53](http://www.open-video.org/details.php?videoid=750) | The Future of Energy Gases, segment 09 | 1,884 | 1:02 | [v53](https://github.com/sandraavila/vsumm/blob/main/Results/video53.pdf)
[v54](http://www.open-video.org/details.php?videoid=753) | The Future of Energy Gases, segment 10 | 2,886 | 1:36 | [v54](https://github.com/sandraavila/vsumm/blob/main/Results/video54.pdf)
[v55](http://www.open-video.org/details.php?videoid=785) | Oceanfloor Legacy, segment 01 | 1,740 | 0:58 | [v55](https://github.com/sandraavila/vsumm/blob/main/Results/video55.pdf)
[v56](http://www.open-video.org/details.php?videoid=786) | Oceanfloor Legacy, segment 02 | 2,325 | 1:17 | [v56](https://github.com/sandraavila/vsumm/blob/main/Results/video56.pdf)
[v57](http://www.open-video.org/details.php?videoid=788) | Oceanfloor Legacy, segment 04 | 3,450 | 1:55 | [v57](https://github.com/sandraavila/vsumm/blob/main/Results/video57.pdf)
[v58](http://www.open-video.org/details.php?videoid=792) | Oceanfloor Legacy, segment 08 | 3,186 | 1:46 |[v58](https://github.com/sandraavila/vsumm/blob/main/Results/video58.pdf)
[v59](http://www.open-video.org/details.php?videoid=793) | Oceanfloor Legacy, segment 09 | 2,106 | 1:10 | [v59](https://github.com/sandraavila/vsumm/blob/main/Results/video59.pdf)
[v60](http://www.open-video.org/details.php?videoid=803) | The Voyage of the Lee, segment 05 | 2,094 | 1:09 | [v60](https://github.com/sandraavila/vsumm/blob/main/Results/video60.pdf)
[v61](http://www.open-video.org/details.php?videoid=813) | The Voyage of the Lee, segment 15 | 2,094 | 1:15 | [v61](https://github.com/sandraavila/vsumm/blob/main/Results/video61.pdf)
[v62](http://www.open-video.org/details.php?videoid=814) | The Voyage of the Lee, segment 16 | 2,619 | 1:27 | [v62](https://github.com/sandraavila/vsumm/blob/main/Results/video62.pdf)
[v63](http://www.open-video.org/details.php?videoid=838) | Hurricane Force - A Coastal Perspective, segment 03 | 2,310 | 1:17 | [v63](https://github.com/sandraavila/vsumm/blob/main/Results/video63.pdf)
[v64](http://www.open-video.org/details.php?videoid=839) | Hurricane Force - A Coastal Perspective, segment 04 | 5,310 | 2:57 | [v64](https://github.com/sandraavila/vsumm/blob/main/Results/video64.pdf)
[v65](http://www.open-video.org/details.php?videoid=850) | Drift Ice as a Geologic Agent, segment 03 | 5,310 | 1:31 | [v65](https://github.com/sandraavila/vsumm/blob/main/Results/video65.pdf)
[v66](http://www.open-video.org/details.php?videoid=852) | Drift Ice as a Geologic Agent, segment 05 | 2,187 | 1:12 | [v66](https://github.com/sandraavila/vsumm/blob/main/Results/video66.pdf)
[v67](http://www.open-video.org/details.php?videoid=853) | Drift Ice as a Geologic Agent, segment 06 | 2,425 | 1:30 | [v67](https://github.com/sandraavila/vsumm/blob/main/Results/video67.pdf)
[v68](http://www.open-video.org/details.php?videoid=854) | Drift Ice as a Geologic Agent, segment 07 | 1,950 | 1:05 | [v68](https://github.com/sandraavila/vsumm/blob/main/Results/video68.pdf)
[v69](http://www.open-video.org/details.php?videoid=855) | Drift Ice as a Geologic Agent, segment 08 | 3,618 | 2:00 | [v69](https://github.com/sandraavila/vsumm/blob/main/Results/video69.pdf)
[v70](http://www.open-video.org/details.php?videoid=857) | Drift Ice as a Geologic Agent, segment 10 | 1,407 | 0:46 | [v70](https://github.com/sandraavila/vsumm/blob/main/Results/video70.pdf)



# Citation
```
@article{de2011vsumm,
  title={VSUMM: A mechanism designed to produce static video summaries and a novel evaluation method},
  author={De Avila, Sandra Eliza Fontes and Lopes, Ana Paula Brandao and da Luz Jr, Antonio and de Albuquerque Ara{\'u}jo, Arnaldo},
  journal={Pattern recognition letters},
  volume={32},
  number={1},
  pages={56--68},
  year={2011},
  publisher={Elsevier}
}
```

# Acknowledgments
The authors are grateful to CNPq, CAPES and FAPEMIG, Brazilian research funding agencies, for the financial support to this work.
