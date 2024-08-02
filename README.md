
<p align="center">
  <img src="everyoneiswinner.webp" width="300" title="hover text">
</p>

<p align="justify">This reproducibility package was prepared for the paper titled "Everyone's a Winner! On Hyperparameter Tuning of Recommendation Models" and submitted to the ACM RecSys '23 Conference. The results reported in this paper were achieved with the help of the Elliot Framework. Please refer to the official <a href="https://elliot.readthedocs.io/en/latest/guide/introduction.html">web documentation</a> and <a href="https://github.com/sisinflab/elliot">GitHub</a> page for further information.</p> 

<p align="justify">This shared repository contains the configuration files and datasets, which were used in this analysis. Especially, there are two type of configuration files inside the "config_files" folder. The <em>“tuned”</em> configuration files contain different ranges of hyperparameters and these files are used to tune the algorithms. The “untuned” configuration files contain randomly selected hyperparameters. The optimal values of the hyperparameters for each model, dataset and the performance of the algorithms when using additional metrics can be found in the folder named <em>“Additional material”</em>. Moreover, <b>the list of examined papers</b> for the analysis provided in Section 2 of the paper and results with additional metrics can be seen <a href="https://faisalse.github.io/RecSys2023_hyperparameter_tuning/">here.</a></p>
<h3>Installation guide</h3>
<p>Elliot works with the following operating systems:</p>
<ul>
  <li>Linux</li>
  <li>Windows 10</li>
  <li>macOS X</li>
</ul> 
<p>Elliot requires Python version 3.6 or later.
<br>
Elliot requires tensorflow version 2.3.2 or later. If you want to use Elliot with GPU, please ensure that CUDA or cudatoolkit version is 7.6 or later. This requires NVIDIA driver version >= 10.1 (for Linux and Windows10).</p>
<h4>Install from source</h4>
<h4>CONDA</h4>


<p>
<ul>
  <li>Open the anaconda command prompt to download GitHub repo<em>"RecSys2023_hyperparameter_tuning"</em></li>
  <li>Move to the directory where you want to store the GitHub repo<em>"RecSys2023_hyperparameter_tuning"
</em></li>
  <li>Run the following command to create <em>"elliot_env"</em> environment</li>
</ul> 
</p>
<pre>
  git clone https://github.com/Faisalse/RecSys2023_hyperparameter_tuning.git
  conda create --name elliot_env python=3.8
</pre>

<p>Activate the conda environment</p>
<pre>
  conda activate elliot_env
</pre>

<p>Change to the <em>"hyperparameter_tuning"</em> directory and run this line to install the required packages</p>
<pre>
  pip install -r requirements.txt
</pre>

<p>Installing required packages, run this line to reproduce the results
<pre>
  python reproducibility.py
</pre>

<p align="justify">By default, "Untuned_movieLenz.yml" configuration file is used to reproduce the results for the MovieLens dataset. Different configuration files are available in the “config_files” folder, which are used in our experiments. So, the desired one can be picked and writes its name in <em>"reproducibility.py"</em> file and runs it again to reproduce the results.

<h3>Datasets</h3>
<p align="justify">In the <em>"data"</em> folder, you can find (MovieLens 1M, Amazon Digital Music, Epinions) datasets, which are used in this reproducibility study. We also share the original data file and split version of each dataset to carry out the experiments with the exact same setting. The table below shows the statistics of the selected datasets. The same p-core and the same threshold values (MovieLens 1M, Amazon Digital Music datasets) are used as mentioned in [1]. The p-core filter out the number of items and users lower than given k-core while the threshold parameter assumes single system-wide threshold to filter out irrelevant transactions, which received ratings < 4. </p>

<p align="justify">
<code>
[1] Anelli, Vito Walter, et al. "Top-n recommendation algorithms: A quest for the state-of-the-art." Proceedings of the 30th ACM Conference on User Modeling, Adaptation and Personalization. 2022.
</code></p>

<table style="width:100%">
  <tr style="text-align: center">
    <th >Dataset</th>
    <th>Original transactions</th>
    <th>Original users</th>
    <th>Original items	</th>
    <th>p-core</th>
    <th>threshold</th>
  </tr>
  <tr>
    <td><b>MovieLens 1M</b>	</td>
    <td>1000209</td>
    <td>6040</td>
    <td>3706</td>
    <td>10</td>
    <td>4</td>
  </tr>
  <tr>
    <td><b>Amazon Digital Music</b></td>
    <td>1584082</td>
    <td>840372</td>
    <td>840372</td>
    <td>5</td>
    <td>4</td>
  </tr>
  <tr>
    <td><b>Epinions</b></td>
    <td>300548</td>
    <td>8514</td>
    <td>8510</td>
    <td>2</td>
    <td>/</td>
  </tr>
</table>
