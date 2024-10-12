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

<table xmlns="http://www.w3.org/1999/xhtml" border="1" bordercolor="#888888" cellspacing="0" style="border-color:rgb(136,136,136);border-width:1px;border-collapse:collapse" data-table-local-id="table-2">
  <tbody>
    <tr>
      <td style="text-align:center;width:128px;height:16px">
        File (zip)
      </td>
      <td style="text-align:center;width:99px;height:16px">
        Size (MB)
      </td>
      <td style="text-align:center;width:526px;height:16px">Description</td>
    </tr>
    <tr>
      <td style="text-align:center;width:128px;height:64px">
        <a href="https://www.dropbox.com/s/g0e64b4qfnuual1/database.zip" rel="nofollow" target="_blank">Dataset</a>
      </td>
      <td style="text-align:center;width:99px;height:64px">
        763
      </td>
      <td style="text-align:left;width:526px;height:64px">
        50 videos from
        <a href="http://www.open-video.org/" rel="nofollow" target="_blank">Open Video</a>. All videos are in MPEG-1 format (30 fps, 352 x 240 pixels), in color and with sound. These videos are distributed among several genres (documentary, educational, ephemeral, historical, lecture) and their duration varies from 1 to 4 minutes and approximately 75 minutes of video in total.
        <br />
      </td>
    </tr>
    <tr>
      <td style="text-align:center;width:128px;height:48px">
        <a href="https://www.dropbox.com/s/ilt1jpclzs2o18v/UserSummary.zip" rel="nofollow" target="_blank">User summary</a>
      </td>
      <td style="text-align:center;width:99px;height:48px">
        31.5
      </td>
      <td style="text-align:left;width:526px;height:48px">
        250 user summaries. These summaries were created manually by 50 users, each one dealing with 5 videos, meaning that each video has 5 video summaries created by 5 different users.
      </td>
    </tr>
    <tr>
      <td style="text-align:center;width:128px;height:17px">
        <a href="https://www.dropbox.com/s/47rxdjw34r8dav6/VSUMM1Summary.zip" rel="nofollow" target="_blank">
          VSUMM
          <sub>1</sub>
          summary
        </a>
        <a href="http://www.npdi.dcc.ufmg.br/VSUMM/downloads/VSUMM2Summary.zip" rel="nofollow"></a>
      </td>
      <td style="text-align:center;width:99px;height:17px">6.28</td>
      <td style="text-align:left;width:526px;height:17px">50 video summaries (ours).</td>
    </tr>
    <tr>
      <td style="text-align:center;width:128px;height:17px">
        <a href="https://www.dropbox.com/s/rxuzmg75qvgmy20/VSUMM2Summary.zip" rel="nofollow" target="_blank">VSUMM<sub>2</sub> summary
        </a>
      </td>
      <td style="text-align:center;width:99px;height:17px">4.91</td>
      <td style="text-align:left;width:526px;height:17px">50 video summaries (ours).</td>
    </tr>
    <tr>
      <td style="text-align:center;width:128px;height:16px">
        <a href="https://www.dropbox.com/s/2lyz13xdq0ru798/OVSummary.zip" rel="nofollow" target="_blank">OV summary</a>
      </td>
      <td style="text-align:center;width:99px;height:16px">
        6.30
      </td>
      <td style="text-align:left;width:526px;height:16px">50 video summaries (dataset providers).</td>
    </tr>
    <tr>
      <td style="text-align:center;width:128px;height:48px">
        <a href="https://www.dropbox.com/s/mj3qsvmj7vykx7n/DTSummary.zip" rel="nofollow" target="_blank">DT summary</a>
      </td>
      <td style="text-align:center;width:99px;height:48px">
        3.68
      </td>
      <td style="text-align:left;width:526px;height:48px">
        50 video summaries <a href="http://dx.doi.org/10.1007/s00799-005-0129-9" rel="nofollow" target="_blank">[Mundur et al., 2006]</a>.
      </td>
    </tr>
    <tr>
      <td style="text-align:center;width:128px;height:48px">
        <a href="https://www.dropbox.com/s/lt5tuh9xejp7wm2/STIMOSummary.zip" rel="nofollow" target="_blank">STIMO summary</a>
        (extended version of
        <a href="http://doi.acm.org/10.1145/1282280.1282370" rel="nofollow" target="_blank">VISTO approach</a>
        )
      </td>
      <td style="text-align:center;width:99px;height:48px">
        5.86
      </td>
      <td style="text-align:left;width:526px;height:48px">
        50 video summaries 
        <a href="http://portal.acm.org/citation.cfm?id=1713242" rel="nofollow" target="_blank">[Furini et al., 2010]</a>.
      </td>
    </tr>
  </tbody>
</table>

<table xmlns="http://www.w3.org/1999/xhtml" border="1" bordercolor="#888888" cellspacing="0" style="border-color:rgb(136,136,136);border-width:1px;border-collapse:collapse" data-table-local-id="table-3">
  <tbody>
    <tr>
      <td style="text-align:center;width:125px;height:21px">
         File (zip)
      </td>
      <td style="text-align:center;width:93px;height:21px">
         Size (MB)
      </td>
      <td style="text-align:center;width:536px;height:21px"> Description</td>
    </tr>
    <tr>
      <td style="text-align:center;width:125px;height:63px">
        <a href="https://www.dropbox.com/s/wxpj91cm9m3ikn0/newDatabase.zip" rel="nofollow" target="_blank">Database</a>
      </td>
      <td style="text-align:center;width:93px;height:63px">
        468
      </td>
      <td style="width:536px;height:63px">
        50 video from websites like YouTube. These videos are distributed among several genres (cartoons, news, sports, commercials, tv-shows and home videos) and their duration varies from 1 to 10 minutes.
      </td>
    </tr>
    <tr>
      <td style="text-align:center;width:128px;height:48px">
        <a href="https://www.dropbox.com/s/7rtbyeo64hk8ot7/newUserSummary.zip" rel="nofollow" target="_blank">User summary</a>
      </td>    
      <td style="text-align:center;width:93px;height:63px">
        45.3
      </td>
      <td style="width:536px;height:63px">250 user summaries. These summaries were created manually by 50 users, each one dealing with 5 videos, meaning that each video has 5 video summaries created by 5 different users.</td>
    </tr>
    <tr>
      <td style="text-align:center;width:125px;height:21px"><a href="https://www.dropbox.com/s/2f448wsndg2877r/VSUMMSummary.zip" rel="nofollow" target="_blank">VSUMM summary</a>
      </td>
      <td style="text-align:center;width:93px;height:21px">
        7.93
      </td>
      <td style="width:536px;height:21px">50 video summaries (ours).</td>
    </tr>
  </tbody>
</table>

# Comparison of User Summaries (CUS) 
CUS evaluation method (jar, example) (update on February 2014). The jai_core and jai_codec were included in the CUS implementation.

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
* `-t [threshold (default: 0.5)]`: CUS evaluation method compares each user summary directly with the automatic summaries. For comparing keyframes from different summaries, the color histogram are applied and the distance among them is measured by Manhattan distance. Two keyframes are similar if the distance between them is less than a predetermined threshold. Once two frames are matched, they are removed from the next iteration of the comparing procedure. The default value is 0.5.

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
