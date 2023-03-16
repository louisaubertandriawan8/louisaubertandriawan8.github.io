<hr>
<h2 id="title-analisis-ragam-2-arah-dengan-interaksi-untuk-mengetahui-pengaruh-temperatur-dan-kebisingan-terhadap-kerja-sistem-cardiovaskuler-operator-produksi-subtitle-studi-kasus-pt-general-electric-lighting-indonesia-author-louis-aubert-andriawan-date-mei-2022-output---prettydochtml_pretty-----theme-architect-----highlight-github-----toc-true-----number_sections-true">title: &quot;Analisis Ragam 2 Arah dengan Interaksi untuk Mengetahui Pengaruh Temperatur dan Kebisingan Terhadap Kerja Sistem <em>Cardiovaskuler</em> Operator Produksi&quot;
subtitle: &quot;(Studi Kasus PT General Electric Lighting Indonesia)&quot;
author: &quot;Louis Aubert Andriawan&quot;
date: &quot;Mei 2022&quot;
output:
  prettydoc::html_pretty:
    theme: architect
    highlight: github
    toc: true
    number_sections: true</h2>
<pre><code class="language-{r">library(knitr)
opts_chunk$set(message = FALSE)
opts_chunk$set(warning = FALSE)
opts_chunk$set(comment = &quot;&quot;)
opts_chunk$set(collapse = TRUE)
opts_chunk$set(error = TRUE)
opts_chunk$set(prompt = TRUE)
opts_chunk$set(fig.align = &#39;center&#39;)
</code></pre>
<h1 id="pendahuluan">PENDAHULUAN</h1>
<h2 id="latar-belakang">Latar Belakang</h2>
<p>  Perkembangan industri di Indonesia tidak hanya membawa dampak positif bagi pertumbuhan perekonomian bangsa Indonesia. Di sisi lain, ada juga dampak negatif yang dihasilkan. Dampak negatif tersebut akan meningkatkan potensi bahaya dan penyakit akibat kerja. Potensi bahaya tersebut bisa muncul dari lingkungan kerja, bahan produksi, proses produksi, dan lain-lain. Sumber-sumber bayaha tersebut jika tidak dikendalikan secara optimal dapat mengakibatkan kecelakaan dan penyakit akibat kerja.  </p>
<p>  Salah satu potensi bahaya dan penyakit akibat kerja yang dialami tenaga kerja adalah penyakit <em>cardiovaskuler</em>. Berdasarkan data International Labor Organization tahun 1999, penyakit <em>cardiovaskuler</em> berada di peringkat empat sebagai penyakit akibat kerja yang paling sering terjadi. Data tersebut diramalkan akan semakin meningkat seiring dengan perkembangan teknologi permesinan. Penyakit <em>cardiovaskuler</em> adalah penyakit yang diakibatkan karena tidak berfungsinya sistem peredaran darah, seperti jantung, darah, dan pembuluh darah dengan baik.  </p>
<p>  Menurut Ganong (1983) di dalam buku <em>Review of Medical Physiology</em>,
terdapat faktor-faktor yang menyebabkan frekuensi denyut jantung meningkat atau menurun. Frekuensi denyut jantung menjadi meningkat karena disebabkan oleh keadaan emosi (gelisah, gembira), temperatur lingkungan yang tinggi, kondisi setelah makan, aktivitas kerja, kehamilan, konsumsi rokok dan obat-obatan yang meningkatkan kerja sistem saraf simpatis. Sedangkan penyakit jantung, kondisi tidur dan istirahat dapat mengurangi frekuensi denyut jantung. Hal yang serupa juga diungkapkan Nurmianto (1995), temperatur sekeliling yang tinggi dan tingginya pembebanan otot akan menyebabkan frekuensi denyut
jantung meningkat. Kondisi lingkungan yang bising terus menerus juga akan meningkatkan frekuensi denyut jantung (Arifiani, 2006).  </p>
<p>  Dalam melindungi tenaga kerja, khususnya operator bagian produksi, PT GE Lighting Indonesia mempunyai satu divisi khusus yang bertanggung jawab dalam mengelola keselamatan dan kesehatan tenaga kerja, yaitu departemen <em>Environmental Health and Safety</em> (EHS). Dalam menjalankan tugasnya, departemen EHS membuat peraturan keselamatan dan kesehatan kerja yang harus dilaksanakan oleh semua orang yang berada di lingkungan PT GE Lighting Indonesia.  </p>
<p>  Kebijakan tersebut antara lain adalah penggunaan alat pelindung diri seperti <em>ear plug</em> (pelindung telinga), kacamata pelindung, sarung tangan, masker, dan sepatu pelindung. Namun dalam pelaksanaannya, masih terdapat ketidakdisiplinan tenaga kerja dalam menggunakan alat pelindung kesehatan.  </p>
<p>  Keadaan lingkungan fisik di PT GE Lighting Indonesia dapat dikategorikan sebagai kondisi yang tidak ergonomis. Tingkat kebisingan lantai produksi lebih dari 85 dB atau berada di atas nilai ambang batas kebisingan. Sumber kebisingan berasal dari mesin-mesin produksi yang berjumlah 8-9 buah mesin di setiap <em>line</em> produksi. Mesin-mesin yang digunakan dalam proses produksi pembuatan lampu mengakibatkan tempat produksi menjadi panas, dengan temperatur mencapai $30^{\circ}$C. Pada kondisi lingkungan yang ergonomis, temperatur lingkungan kerja sebesar $24^{\circ}$C - $26^{\circ}$C. Bekerja di lingkungan yang panas dengan ventilasi yang kurang baik serta pada tingkat kebisingan yang tinggi dapat menjadi akar masalah kesehatan operator produksi.  </p>
<p>  Pada penelitian ini, terdapat 2 faktor yang akan dianalisis, yaitu faktor temperatur dan kebisingan. Kedua faktor tersebut akan dianalisis menggunakan Anova 2 arah dengan interaksi untuk mengetahui apakah terdapat pengaruh terhadap kerja sistem <em>cardiovaskuler</em> dan seberapa besar pengaruhnya dengan menggunakn sampel operator produksi di PT GE Lighting Indonesia.</p>
<h2 id="anova-analysis-of-variance">Anova (<em>Analysis of Variance</em>)</h2>
<p>  Anova adalah sebuah analisis untuk melihat perbedaan rata-rata lebih dari dua populasi. Menurut Ronald E. Walpole (1993), analisis ragam (Anova) adalah suatu metode untuk menguraikan keragaman total data menjadi komponen-komponen yang mengukur berbagai sumber keragaman. Anova juga merupakan salah satu alat statistik yang berkaitan dengan pengujian hipotesis mengenai perbedaan rata-rata untuk tiga populasi atau lebih.  </p>
<p>  Dalam uji Anova, ada beberapa asumsi yang harus terpenuhi, antara lain:  </p>
<ul>
<li>Unit observasi diperoleh secara acak dan independen sehingga galat atau error bersifat bebas/independen.  </li>
<li>Populasi yang diuji berdistribusi normal (dapat diuji dengan uji normalitas Shapiro Wilk atau Kolmogorov Smirnov).  </li>
<li>Populasi yang diuji memiliki varians atau ragam yang sama (dapat diuji dengan uji homogenitas ragam yaitu uji Bartlett atau uji Levene).</li>
</ul>
<p>Uji Anova dapat dibedakan berdasarkan banyaknya faktor dalam melakukan pengamatan. Jika faktor pengamatan hanya satu, maka disebut uji Anova satu arah (<em>one way Anova</em>), sedangkan jika terdapat dua faktor, maka disebut uji Anova dua arah (<em>two way Anova</em>). Anova dua arah sendiri dibagi lagi menjadi 2, yaitu tanpa interkasi dan dengan interaksi.  </p>
<p>  Anova 2 arah tanpa interaksi adalah mengasumsikan bahwa faktor pertama dengan faktor kedua bersifat aditif (tidak ada interaksi antar faktor). Sedangkan Anova 2 arah dengan interaksi, selain memperhatikan pengaruh faktor pertama dan faktor kedua, juga diperhatikan apakah ada pengaruh interaksi dari kedua faktor tersebut.  </p>
<h2 id="statistika-deskriptif-dalam-anova">Statistika Deskriptif dalam Anova</h2>
<h3 id="anova-1-arah">Anova 1 Arah</h3>
<p>  Tujuan dari Anova adalah menguraikan jumlah kuadrat total. <strong>Jumlah Kuadrat Total (JKT)</strong> digunakan untuk melihat keragaman total dalam komponen. Pada dasarnya, JKT diuraikan menjadi 2 komponen, yaitu jumlah kuadrat antar perlakuan/treatment (<em>sum square between</em>) yang digunakan untuk melihat keragaman antar perlakuan dan jumlah kuadrat dalam perlakuan/treatment (<em>sum square within</em>) yang digunakan untuk melihat keragaman dalam perlakuan. jumlah kuadrat antar perlakuan/treatment disebut <strong>Jumlah Kuadrat Perlakuan (JKP)</strong>, sedangkan jumlah kuadrat dalam perlakuan/treatment disebut <strong>Jumlah Kuadrat Galat (JKG)</strong>. Penguraian komponen tersebut digunakan untuk Anova 1 arah. Secara matematis, model linear untuk Anova 1 arah adalah<br>$$
x_{ij}=\mu+\alpha_i+\epsilon_{ij}
$$
dimana  </p>
<blockquote>
<p>$\alpha_i$ sebagai pengaruh perlakuan ke-i<br>$\epsilon_{ij}$ sebagai pengaruh yang tak dapat dijelaskan dalam pengamatan dengan perlakuan ke-i dan ulangan ke-j (disebut galat atau residual)  </p>
</blockquote>
<p>Hipotesisnya:<br>$H_0$=$\alpha_1$=$\alpha_2$=...=$\alpha_t$=0<br>$H_1$=sekurang-kurangnya satu $\alpha_i$ tidak sama dengan 0  </p>
<p>Uji akan didasarkan pada perbandingan dua nilai dugaan yang bebas bagi ragam populasi $\sigma^2$. Nilai dugaan itulah yang diperoleh dengan menguraikan keragaman total menjadi dua komponenen.  </p>
<p>  Dapat ditulis sebagai berikut:<br>$$
JKT=JKP+JKG
$$
dengan:<br>$JKT=\sum_{i=1}^{t}\sum_{j=1}^{n}(x_{ij}-\overline{x}<em>{..})^2$<br>$JKP=n\sum</em>{i=1}^{t}(\overline{x}<em>{i.}-\overline{x}</em>{..})^2$<br>$JKG=\sum_{i=1}^{t}\sum_{j=1}^{n}(x_{ij}-\overline{x}_{i.})^2$  </p>
<blockquote>
<p>Keterangan:<br>$x_{ij}=$ nilai pengamatan dari perlakuan ke-i ulangan ke-j<br>$\overline{x}..=$ rata-rata seluruh pengamatan<br>$\overline{x}_{i.}=$ rata-rata pengamatan dari perlakuan ke-i<br>t= banyaknya perlakuan/treatment<br>n= banyaknya ulangan  </p>
</blockquote>
<p>Rumus di atas adalah rumus definisi. Untuk <strong>rumus kerjanya</strong> adalah sebagai berikut:<br>$JKT=\sum_{i=1}^{t}\sum_{j=1}^{n}x_{ij}^2-{FK}$<br>$JKP=\frac{\sum_{i=1}^{t}{x_{i.}^2}}{n}-{FK}$<br>$JKG=JKT-JKP$<br>dengan<br>$FK (Faktor Koreksi)=\frac{x_{..}^2}{nt}$  </p>
<blockquote>
<p>Keterangan:<br>$x_{i.}=$ total nilai pengamatan untuk perlakuan ke-i<br>$x_{..}=$ total nilai seluruh pengamatan  </p>
</blockquote>
<table>
<thead>
<tr>
<th>Sumber Keragaman</th>
<th>Derajat Bebas</th>
<th>Jumlah Kuadrat</th>
<th>Kuadrat Tengah</th>
</tr>
</thead>
<tbody><tr>
<td>Perlakuan</td>
<td>$t-1$</td>
<td>JKP</td>
<td>$\frac{JKP}{t-1}$</td>
</tr>
<tr>
<td>Galat</td>
<td>$n(t-1)$</td>
<td>JKG</td>
<td>$\frac{JKG}{n(t-1)}$</td>
</tr>
<tr>
<td>Total</td>
<td>$nt-1$</td>
<td>JKT</td>
<td></td>
</tr>
</tbody></table>
<p>Table: Tabel Anova 1 arah  </p>
<p>Rumus di atas digunakan apabila jumlah ulangan setiap perlakuan sama. Jika setiap perlakuan memiliki ulangan yang tak sama, maka rumusnya menjadi sebagai berikut:<br>$JKT=\sum_{i=1}^{t}\sum_{j=1}^{n_i}x_{ij}^2-{FK}$<br>$JKP=\sum_{i=1}^{t}\frac{{x_{i.}^2}}{n_i}-{FK}$<br>$JKG=JKT-JKP$<br>dengan<br>$FK (Faktor Koreksi)=\frac{x_{..}^2}{\sum_{i=1}^{t}n_i}$  </p>
<blockquote>
<p>Keterangan:
$n_i=$ banyaknya ulangan untuk perlakuan ke-i    </p>
</blockquote>
<table>
<thead>
<tr>
<th>Sumber Keragaman</th>
<th>Derajat Bebas</th>
<th>Jumlah Kuadrat</th>
<th>Kuadrat Tengah</th>
</tr>
</thead>
<tbody><tr>
<td>Perlakuan</td>
<td>$t-1$</td>
<td>JKP</td>
<td>$\frac{JKP}{t-1}$</td>
</tr>
<tr>
<td>Galat</td>
<td>$\sum_{i=1}^{t}n_i-k$</td>
<td>JKG</td>
<td>$\frac{JKG}{n(t-1)}$</td>
</tr>
<tr>
<td>Total</td>
<td>$\sum_{i=1}^{t}n_i-1$</td>
<td>JKT</td>
<td></td>
</tr>
</tbody></table>
<p>Table: Tabel Anova 1 arah (<strong>ulangan tak sama dalam setiap perlakuan</strong>)</p>
<p>Statistik uji yang digunakan untuk membandingkan keragaman adalah statistik uji F<br>$$
F=\frac{Kuadrat Tengah Perlakuan}{Kuadrat Tengah Galat}
$$
Jika nilai statistik uji F lebih dari nilai $F_{tabel}$, maka keputusannya adalah tolak $H_0$ yang berarti terdapat perbedaan nilai rata-rata antar perlakuan.   </p>
<h3 id="anova-2-arah-tanpa-interaksi">Anova 2 Arah Tanpa Interaksi</h3>
<p>  Untuk Anova 2 arah tanpa interaksi, terdapat 1 komponen lagi yang diuraikan dari JKT. Alasannya adalah karena terdapat 1 faktor tambahan. Jika faktor pertama terletak di baris dan faktor kedua terletak di kolom, maka anggap <strong>Jumlah Kuadrat Baris (JKB)</strong> sebagai sumber keragaman faktor pertama dan <strong>Jumlah Kuadrat Kolom (JKK)</strong> sebagai sumber keragaman faktor kedua. Secara matematis, model linear untuk Anova 2 arah tanpa interaksi adalah<br>$$
x_{ij}=\mu+\alpha_i+\beta_j+\epsilon_{ij}
$$
dimana  </p>
<blockquote>
<p>$\alpha_i$ sebagai pengaruh faktor pertama ke-i<br>$\beta_j$ sebagai pengaruh faktor kedua ke-j<br>$\epsilon_{ij}$ sebagai pengaruh yang tak dapat dijelaskan dalam pengamatan dengan faktor pertama ke-i dan faktor kedua ke-j (disebut galat atau residual)  </p>
</blockquote>
<p>Anova 2 arah tanpa interaksi memiliki 2 hipotesis:  </p>
<ul>
<li>Hipotesis untuk faktor pertama:<br>$H_0:$ $\alpha_1=$ $\alpha_2=...=$ $\alpha_r=0$<br>$H_1:$ sekurang-kurangnya satu $\alpha_i$ tidak sama dengan 0  </li>
<li>Hipotesis untuk faktor kedua:<br>$H_0:$ $\beta_1=$ $\beta_2=...=$ $\beta_c=0$<br>$H_1:$ sekurang-kurangnya satu $\beta_j$ tidak sama dengan 0</li>
</ul>
<p>Penguraian jumlah kuadrat total menjadi 3 komponen, yaitu:<br>$$
JKT=JKB+JKK+JKG
$$
dengan:<br>$JKT=\sum_{i=1}^{r}\sum_{j=1}^{c}(x_{ij}-\overline{x}<em>{..})^2$<br>$JKB=c\sum</em>{i=1}^{r}(\overline{x}<em>i.-\overline{x}</em>{..})^2$<br>$JKK=r\sum_{j=1}^{c}(\overline{x}<em>{.j}-\overline{x}</em>{..})^2$<br>$JKG=\sum_{i=1}^{r}\sum_{j=1}^{c}(x_{ij}-\overline{x}<em>{i.}-\overline{x}</em>{.j}+\overline{x}_{..})^2$  </p>
<blockquote>
<p>Keterangan:<br>$x_{ij}=$ nilai pengamatan dari faktor pertama ke-i dan faktor kedua ke-j<br>$\overline{x}..=$ rata-rata seluruh pengamatan<br>$\overline{x}<em>{i.}=$ rata-rata pengamatan dari faktor pertama ke-i<br>$\overline{x}</em>{.j}=$ rata-rata pengamatan dari faktor kedua ke-j<br>r= banyaknya faktor pertama<br>c= banyaknya faktor kedua   </p>
</blockquote>
<p>Rumus di atas adalah rumus definisi. Untuk <strong>rumus kerjanya</strong> adalah sebagai berikut:<br>$JKT=\sum_{i=1}^{r}\sum_{j=1}^{c}x_{ij}^2-{FK}$<br>$JKB=\frac{\sum_{i=1}^{r}{x_{i.}^2}}{c}-{FK}$<br>$JKK=\frac{\sum_{j=1}^{c}{x_{.j}^2}}{r}-{FK}$<br>$JKG=JKT-JKB-JKK$<br>dengan<br>$FK (Faktor Koreksi)=\frac{x_{..}^2}{rc}$  </p>
<blockquote>
<p>Keterangan:<br>$x_{i.}=$ total nilai pengamatan untuk faktor pertama ke-i<br>$x_{.j}=$ total nilai pengamatan untuk faktor kedua ke-j<br>$x_{..}=$ total nilai seluruh pengamatan  </p>
</blockquote>
<table>
<thead>
<tr>
<th>Sumber Keragaman</th>
<th>Derajat Bebas</th>
<th>Jumlah Kuadrat</th>
<th>Kuadrat Tengah</th>
</tr>
</thead>
<tbody><tr>
<td>Faktor pertama</td>
<td>$r-1$</td>
<td>JKB</td>
<td>$\frac{JKB}{r-1}$</td>
</tr>
<tr>
<td>Faktor kedua</td>
<td>$c-1$</td>
<td>JKK</td>
<td>$\frac{JKK}{c-1}$</td>
</tr>
<tr>
<td>Galat</td>
<td>$(r-1)(c-1)$</td>
<td>JKG</td>
<td>$\frac{JKG}{(r-1)(c-1)}$</td>
</tr>
<tr>
<td>Total</td>
<td>$rc-1$</td>
<td>JKT</td>
<td></td>
</tr>
</tbody></table>
<p>Table: Tabel Anova 2 arah tanpa interaksi  </p>
<p>Statistik uji yang digunakan untuk membandingkan keragaman ada 2 (karena terdapat 2 hipotesis):<br>$$
F_1=\frac{Kuadrat Tengah Faktor Pertama}{Kuadrat Tengah Galat}
$$<br>Jika nilai statistik uji $F_1$ lebih dari nilai $F_{tabel}$, maka keputusannya adalah tolak $H_0$ yang berarti terdapat perbedaan nilai rata-rata antar faktor pertama.<br>$$
F_2=\frac{Kuadrat Tengah Faktor Kedua}{Kuadrat Tengah Galat}
$$
Jika nilai statistik uji $F_2$ lebih dari nilai $F_{tabel}$, maka keputusannya adalah tolak $H_0$ yang berarti terdapat perbedaan nilai rata-rata antar faktor kedua.   </p>
<h3 id="anova-2-arah-dengan-interaksi">Anova 2 Arah dengan Interaksi</h3>
<p>  Jika Anova 2 arah tanpa interaksi hanya ingin mengetahui apakah terdapat pengaruh dari faktor pertama dan faktor kedua tanpa memperhatikan adanya interaksi atau hubungan antara kedua faktor, Anova 2 arah dengan interaksi mempertimbangkan bahwa kedua faktor terdapat interaksi. Umumnya, Anova 2 arah dengan interaksi dilakukan ulangan sebanyak n kali ($n\ge2$) untuk suatu percobaan dengan faktor pertama ke-i dan faktor kedua ke-j. Anova 2 arah dengan interaksi menambahkan 1 komponen baru untuk menguraikan JKT, yaitu <strong>Jumlah Kuadrat Interaksi</strong>. Jumlah Kuadrat Interaksi dapat ditulis JK(BK). Secara matematis, model linear untuk Anova 2 arah dengan interaksi adalah<br>$$
x_{ijk}=\mu+\alpha_i+\beta_j+(\alpha\beta)<em>{ij}+\epsilon</em>{ijk}
$$
dimana  </p>
<blockquote>
<p>$\alpha_i$ sebagai pengaruh faktor pertama ke-i<br>$\beta_j$ sebagai pengaruh faktor kedua ke-j<br>$(\alpha\beta)<em>{ij}$ sebagai pengaruh interaksi antara faktor pertama ke-i dan faktor kedua ke-j<br>$\epsilon</em>{ijk}$ sebagai pengaruh yang tak dapat dijelaskan dalam pengamatan dengan faktor pertama ke-i dan faktor kedua ke-j untuk ulangan ke-k (disebut galat atau residual)  </p>
</blockquote>
<p>Anova 2 arah dengan interaksi memiliki 3 hipotesis:  </p>
<ul>
<li>Hipotesis untuk faktor pertama:<br>$H_0:$ $\alpha_1=$ $\alpha_2=...=$ $\alpha_r=0$<br>$H_1:$ sekurang-kurangnya satu $\alpha_i$ tidak sama dengan 0  </li>
<li>Hipotesis untuk faktor kedua:<br>$H_0:$ $\beta_1=$ $\beta_2=...=$ $\beta_c=0$<br>$H_1:$ sekurang-kurangnya satu $\beta_j$ tidak sama dengan 0  </li>
<li>Hipotesis untuk interaksi:<br>$H_0:$ $(\alpha\beta)<em>{11}=$ $(\alpha\beta)</em>{12}=...=$ $(\alpha\beta)<em>{rc}=0$<br>$H_1:$ sekurang-kurangnya satu $(\alpha\beta)</em>{ij}$ tidak sama dengan 0</li>
</ul>
<p>Penguraian jumlah kuadrat total menjadi 4 komponen, yaitu:<br>$$
JKT=JKB+JKK+JK(BK)+JKG
$$
dengan:<br>$JKT=\sum_{i=1}^{r}\sum_{j=1}^{c}\sum_{k=1}^{n}(x_{ijk}-\overline{x}<em>{...})^2$<br>$JKB=cn\sum</em>{i=1}^{r}(\overline{x}<em>{i..}-\overline{x}</em>{...})^2$<br>$JKK=rn\sum_{j=1}^{c}(\overline{x}<em>{.j.}-\overline{x}</em>{...})^2$<br>$JK(BK)=n\sum_{i=1}^{r}\sum_{j=1}^{c}(\overline{x}<em>{ij.}-\overline{x}</em>{i..}-\overline{x}<em>{.j.}+\overline{x}</em>{...})^2$<br>$JKG=\sum_{i=1}^{r}\sum_{j=1}^{c}\sum_{k=1}^{n}(x_{ijk}-\overline{x}_{ij.})^2$  </p>
<blockquote>
<p>Keterangan:<br>$x_{ijk}=$ nilai pengamatan faktor pertama ke-i, faktor kedua ke-j, ulangan ke-k<br>$\overline{x}<em>{...}=$ rata-rata seluruh pengamatan<br>$\overline{x}</em>{i..}=$ rata-rata pengamatan untuk faktor pertama ke-i<br>$\overline{x}<em>{.j.}=$ rata-rata pengamatan untuk faktor kedua ke-j<br>$\overline{x}</em>{ij.}=$ rata-rata pengamatan untuk faktor pertama ke-i dan faktor kedua ke-j<br>r= banyaknya faktor pertama<br>c= banyaknya faktor kedua<br>n= banyaknya ulangan  </p>
</blockquote>
<p>Rumus di atas adalah rumus definisi. Untuk <strong>rumus kerjanya</strong> adalah sebagai berikut:<br>$JKT=\sum_{i=1}^{r}\sum_{j=1}^{c}\sum_{k=1}^{n}x_{ijk}^2-{FK}$<br>$JKB=\frac{\sum_{i=1}^{r}{x_{i..}^2}}{cn}-{FK}$<br>$JKK=\frac{\sum_{j=1}^{c}{x_{.j.}^2}}{rn}-{FK}$<br>$JK(BK)=\frac{\sum_{i=1}^{r}\sum_{j=1}^{c}{x_{ij.}^2}}{n}-{FK}-JKB-JKK$<br>$JKG=JKT-JKB-JKK-JK(BK)$<br>dengan<br>$FK (Faktor Koreksi)=\frac{x_{...}^2}{rcn}$  </p>
<blockquote>
<p>Keterangan:<br>$x_{i..}=$ total nilai pengamatan untuk faktor pertama ke-i<br>$x_{.j.}=$ total nilai pengamatan untuk faktor kedua ke-j<br>$x_{ij.}=$ total nilai pengamatan untuk faktor pertama ke-i dan faktor kedua ke-j<br>$x_{...}=$ total nilai seluruh pengamatan  </p>
</blockquote>
<table>
<thead>
<tr>
<th>Sumber Keragaman</th>
<th>Derajat Bebas</th>
<th>Jumlah Kuadrat</th>
<th>Kuadrat Tengah</th>
</tr>
</thead>
<tbody><tr>
<td>Faktor pertama</td>
<td>$r-1$</td>
<td>JKB</td>
<td>$\frac{JKB}{r-1}$</td>
</tr>
<tr>
<td>Faktor kedua</td>
<td>$c-1$</td>
<td>JKK</td>
<td>$\frac{JKK}{c-1}$</td>
</tr>
<tr>
<td>Interakasi</td>
<td>$(r-1)(c-1)$</td>
<td>JK(BK)</td>
<td>$\frac{JK(BK)}{(r-1)(c-1)}$</td>
</tr>
<tr>
<td>Galat</td>
<td>$rc(n-1)$</td>
<td>JKG</td>
<td>$\frac{JKG}{rc(n-1)}$</td>
</tr>
<tr>
<td>Total</td>
<td>$rcn-1$</td>
<td>JKT</td>
<td></td>
</tr>
</tbody></table>
<p>Table: Tabel Anova 2 arah dengan interaksi  </p>
<p>Statistik uji yang digunakan untuk membandingkan keragaman ada 3 (karena terdapat 3 hipotesis):<br>$$
F_1=\frac{Kuadrat Tengah Faktor Pertama}{Kuadrat Tengah Galat}
$$<br>Jika nilai statistik uji $F_1$ lebih dari nilai $F_{tabel}$, maka keputusannya adalah tolak $H_0$ yang berarti terdapat perbedaan nilai rata-rata antar faktor pertama.<br>$$
F_2=\frac{Kuadrat Tengah Faktor Kedua}{Kuadrat Tengah Galat}
$$
Jika nilai statistik uji $F_2$ lebih dari nilai $F_{tabel}$, maka keputusannya adalah tolak $H_0$ yang berarti terdapat perbedaan nilai rata-rata antar faktor kedua.<br>$$
F_3=\frac{Kuadrat Tengah Interaksi}{Kuadrat Tengah Galat}
$$
Jika nilai statistik uji $F_3$ lebih dari nilai $F_{tabel}$, maka keputusannya adalah tolak $H_0$ yang berarti terdapat interaksi antar dua faktor yang menyebabkan perbedaan nilai rata-rata antar kedua faktor.   </p>
<h2 id="uji-perbandingan-berganda-multiple-comparison">Uji Perbandingan Berganda (<em>Multiple Comparison</em>)</h2>
<p>  Uji perbandingan berganda dapat dilakukan dengan berbagai uji, seperti uji Nyata Terkecil Fisher (<em>Least Significance Difference</em>), uji Nyata Jujur Tukey (<em>Honestly Significance Difference</em>), uji Duncan, uji Bonferroni, dan lain sebagainya. Uji ini dilakukan untuk melihat perbandingan tiap kelompok dari analisis sebelumnya. Uji perbandingan berganda dilakukan saat ada pengaruh yang nyata antar faktor. Dengan uji perbandingan berganda, akan dicari pasangan faktor mana yang saling berbeda secara statistik. Contoh uji perbandingan yang akan dibahas adalah uji Nyata Terkecil Fisher dan uji Tukey HSD.  </p>
<h3 id="uji-nyata-terkecil-fisher-uji-bnt">Uji Nyata Terkecil Fisher (Uji BNT)</h3>
<p>Hipotesisnya<br>$H_0:$ $\mu_i-\mu_{i&#39;}=0$<br>$H_1:$ $\mu_i-\mu_{i&#39;}\ne0$<br>Untuk seluruh pasangan faktor $i$ dan $i&#39;$<br>Statistik ujinya:<br>$$
BNT=t_{\alpha/2,dbGalat}\sqrt{KTG(\frac{1}{n_i}+\frac{1}{n_{i&#39;}})}
$$
Jika $|\overline{X}<em>{i}-\overline{X}</em>{i&#39;}|&gt;BNT$, maka tolak $H_0$ yang berarti pasangan faktor $i$ dengan $i&#39;$ dinyatakan berbeda.  </p>
<h3 id="uji-tukey-hsd-uji-bnj">Uji Tukey HSD (Uji BNJ)</h3>
<p>Hipotesisnya<br>$H_0:$ $\mu_i-\mu_{i&#39;}=0$<br>$H_1:$ $\mu_i-\mu_{i&#39;}\ne0$<br>Untuk seluruh pasangan faktor $i$ dan $i&#39;$<br>Statistik ujinya:<br>$$
BNJ=\frac{q_{\alpha/2,t,dbGalat}}{\sqrt{2}}\sqrt{KTG(\frac{1}{n_i}+\frac{1}{n_{i&#39;}})}
$$</p>
<blockquote>
<p>$q_{\alpha/2,t,dbGalat}$ adalah titik kritis tabel studentized range, di mana t adalah banyaknya faktor atau perlakuan  </p>
</blockquote>
<p>Jika $|\overline{X}<em>{i}-\overline{X}</em>{i&#39;}|&gt;BNJ$, maka tolak $H_0$ yang berarti pasangan faktor $i$ dengan $i&#39;$ dinyatakan berbeda.  </p>
<h2 id="effect-size-eta-squared">Effect Size (Eta Squared)</h2>
<p>  Eta squared berfungsi untuk mengukur seberapa besar pengaruh dari sebuah faktor yang dapat menjelaskan respons.  </p>
<p>  Rumus Eta Squared:<br>$$
\eta^2=\frac{JK_{faktor}}{JKT}
$$
  Jika terdapat lebih dari 1 faktor, rumus di atas dapat menyebabkan variabilitas dari suatu faktor akan tersarang dalam JKT. Sehingga tidak bisa mengetahui variabilitas dari satu faktor itu saja. Oleh sebab itu, digunakan Partial Eta Squared.  </p>
<p>  Rumus Partial Eta Squared:<br>$$
\eta^2_{partial}=\frac{JK_{faktor}}{JK_{faktor}+JKG}
$$  </p>
<h2 id="uji-beda-rata-rata-2-sampel-independen">Uji Beda Rata-Rata 2 Sampel Independen</h2>
<p>  Uji beda rata-rata dua sampel independen dilakukan ketika terdapat dua populasi ingin diteliti apakah rata-rata antar kedua populasi tersebut sama atau tidak. Hipotesis awal dari uji ini adalah rata-rata antar kedua sampel adalah sama, sedangkan hipotesis alternatifnya bisa satu diantara tiga kemungkinan (rata-rata kedua populasi tidak sama, rata-rata populasi pertama lebih besar daripada populasi kedua, atau rata-rata populasi pertama lebih kecil daripada populasi kedua)  </p>
<p>  Hipotesisnya dapat ditulis sebagai berikut:<br>$H_0:\mu_1=\mu_2$<br>$H_1:\begin{cases} \mu_1\ne\mu_2 \ \mu_1&gt;\mu_2  \ \mu_1&lt;\mu_2     \end{cases}$  </p>
<p>  Untuk ragam dianggap sama, maka statistik ujinya adalah sebagai berikut<br>$$
t_{hit}=\frac{(\overline{x}<em>{1}-\overline{x}</em>{2})-(\mu_1-\mu_2)}{s_p\sqrt{\frac{1}{n_1}+\frac{1}{n_2}}}
$$<br>dengan
$s_p^2=\frac{s_1^2(n_1-1)+s_2^2(n_2-1)}{n_1+n_2-2}$</p>
<h2 id="data">Data</h2>
<p>Pengumpulan data dilakukan di departemen <em>Incandescent and Circular Flourescent</em> PT General Electric Lighting Indonesia. Pengambilan sampel memakai metode <em>purposive sampling</em>, dimana operator sengaja dipilih oleh peneliti karena memenuhi syarat sebagai sampel yang sesuai dengan tujuan penelitian, yaitu:  </p>
<ul>
<li>Jenis kelamin wanita  </li>
<li>Usia 30-40 tahun  </li>
<li>Dalam kondisi sehat  </li>
<li>Tidak dalam keadaan hamil  </li>
<li>Tidak sedang mengonsumsi obat-obatan yang dapat meningkatkan kerja jantung  </li>
<li>Tidak merokok  </li>
<li>Frekuensi olahraga &lt;2 kali per minggu</li>
<li>Masa kerja operator lebih dari 5 tahun</li>
</ul>
<p>Pengukuran denyut jantung dilakukan pada saat operator selesai bekerja dan diukur dalam posisi duduk menggunakan tensimeter digital.  </p>
<p>Faktor pertama yang digunakan adalah Suhu dengan 2 level, yaitu $25^{\circ}$C - $26^{\circ}$C dan $29^{\circ}$C - $30^{\circ}$C. Pengukuran suhu menggunakan termometer ruangan. Faktor kedua yang digunakan adalah Kebisingan dengan 2 level, yaitu 83-84 dB dan 87-88 dB. Pengukuran tingkat kebisingan menggunakan sound level meter. Simbol dan simbol level dari kedua faktor ditampilkan dalam tabel berikut</p>
<pre><code class="language-{r,">library(kableExtra)
collapse_rows_1 &lt;- data.frame(Faktor=c(rep(&quot;Suhu&quot;, 2), rep(&quot;Kebisingan&quot;, 2)),
                 Simbol = c(rep(&quot;A&quot;, 2), rep(&quot;B&quot;, 2)),
                 Level = c(&quot;25°C - 26°C&quot;, &quot;29°C - 30°C&quot;, &quot;83-84 dB&quot;, &quot;87-88 dB&quot;), 
                 Simbol_level = c(&quot;A1&quot;, &quot;A2&quot;, &quot;B1&quot;, &quot;B2&quot;))
kbl(collapse_rows_1, align = &quot;c&quot;) %&gt;%
  kable_paper(full_width = F) %&gt;%
  column_spec(1, bold = T) %&gt;%
  collapse_rows(columns = 1:2)
</code></pre>
<p>Sedangkan variabel respon yang diukur adalah frekuensi denyut jantung kerja operator dalam satuan per menit. Setiap perlakuan dilakukan pengulangan sebanyak sepuluh kali, yang berarti menggunakan 10 operator berbeda. Pengukuran frekuensi denyut jantung dilakukan setelah operator bekerja selama 4 jam.  </p>
<p>Berikut merupakan hasil pengukuran yang disajikan dalam tabel berikut  </p>
<pre><code class="language-{r,">library (knitr)
library(kableExtra)
collapse_rows_2 &lt;- data.frame(B_A=c(rep(&quot;B1&quot;, 10), rep(&quot;B2&quot;, 10)),
                              &quot;A1&quot;=c(76,80,82,78,69,76,79,81,74,81, 83,79,80,84,82,84,78,79,81,79), 
                              &quot;A2&quot;=c(81,79,82,81,77,81,80,81,75,84, 84,88,86,83,84,86,79,92,90,86))
kbl(collapse_rows_2, align = &quot;c&quot;) %&gt;%
  kable_paper(full_width = F) %&gt;%
  column_spec(1, bold = T) %&gt;%
  collapse_rows(columns = 1)
</code></pre>
<h1 id="source-code">SOURCE CODE</h1>
<h2 id="library-yang-dibutuhkan">Library yang Dibutuhkan</h2>
<pre><code class="language-{r,"># library(readr) -&gt; membaca file csv hasil import
# library(rmarkdown) -&gt; menampilkan data dalam bentuk page
# library(tseries) -&gt; uji Normalitas dengan jarque.bera.test  
# libary(car) -&gt; uji Homogenitas Ragam dengan leveneTest  
# library(lsr) -&gt; menghitung eta squared  
</code></pre>
<h2 id="import-data">Import Data</h2>
<pre><code class="language-{r}">library(readr)
library(rmarkdown)
Cardio &lt;- read_csv(&quot;C:/Users/Louis Aubert/Documents/Cardio.csv&quot;)
data&lt;-Cardio
data$Bising&lt;-as.factor(data$Bising)
data$Temp&lt;-as.factor(data$Temp)
paged_table(as.data.frame(data))
</code></pre>
<h2 id="boxplot">Boxplot</h2>
<pre><code class="language-{r}">boxplot(data$`Denyut Jantung`~data$Bising, xlab=&quot;Tingkat Kebisingan (dB)&quot;, ylab = &quot;Denyut Jantung (per menit)&quot;, main=&quot;Boxplot Tingkat Kebisingan terhadap Denyut Jantung&quot;, col=c(&quot;green&quot;, &quot;orange&quot;))

boxplot(data$`Denyut Jantung`~data$Temp, xlab=&quot;Temperatur(°C)&quot;, ylab = &quot;Denyut Jantung (per menit)&quot;, main=&quot;Boxplot Temperatur terhadap Denyut Jantung&quot;, col=c(&quot;blue&quot;, &quot;red&quot;))

boxplot(data$`Denyut Jantung`~data$Temp + data$Bising, xlab=&quot;Temperatur (°C) dan Tingkat Kebisingan (dB)&quot;, ylab = &quot;Denyut Jantung (per menit)&quot;, main=&quot;Boxplot Temperatur dan Tingkat Kebisingan terhadap  
        Denyut Jantung&quot;,col=c(&quot;cyan&quot;, &quot;yellow&quot;, &quot;gray&quot;, &quot;darkred&quot;))
</code></pre>
<p>  Dari boxplot tingkat kebisingan terhadap denyut jantung, secara visual terdapat perbedaan rata-rata denyut jantung antara tingkat kebisingan B1(83-84 dB) dengan B2(87-88 dB) di mana tingkat kebisingan B2 berdampak pada denyut jantung yang lebih tinggi.  </p>
<p>  Dari boxplot temperatur terhadap denyut jantung, secara visual terdapat perbedaan rata-rata denyut jantung antara tingkat kebisingan B1(83-84 dB) dengan B2(87-88 dB) di mana temperatur A2 berdampak pada denyut jantung yang lebih tinggi.  </p>
<p>  Dari boxplot temperatur dan tingkat kebisingan terhadap denyut jantung, secara visual terdapat perbedaan rata-rata denyut jantung untuk interaksi A2.B2 dengan interaksi lainnya. Namun, perbedaan tersebut belum tentu terdapat interaksi di antara temperatur dan tingkat kebisingan.  </p>
<h2 id="asumsi-asumsi">Asumsi-Asumsi</h2>
<h3 id="asumsi-normalitas">Asumsi Normalitas</h3>
<p>Asumsi normalitas dapat diidentifikasi secara visual menggunakan Q-Q Plot dan uji normalitas statistik seperti Jarque Bera, Anderson Darling, dan Shapiro Wilk  </p>
<h4 id="asumsi-normalitas-dengan-q-q-plot">Asumsi Normalitas dengan Q-Q Plot</h4>
<pre><code class="language-{r}">anova&lt;-aov(`Denyut Jantung`~Bising*Temp, data=data)
plot(anova, 2)
</code></pre>
<blockquote>
<ul>
<li><code>aov()</code> berfungsi untuk melakukan uji Anova. Dalam kasus ini, yang diuji adalah Denyut Jantung sebagai fungsi dari interaksi antara Tingkat Kebisingan dan Temperatur. Simbol * di antara dua faktor menandakan uji dilakukan menggunakan interaksi.    </li>
<li>Plot yang ditampilkan adalah Q-Q Plot model Anova 2 arah dengan interkasi. Simbol * menandakan uji yang dilakukuan adalah dengan interaksi. Angka 2 merupakan opsi untuk menampilkan Q-Q Plot.</li>
</ul>
</blockquote>
<p>Karena titik-titik tersebar di sekitar garis, maka dapat diasumsikan data menyebar secara normal.  </p>
<h4 id="asumsi-normalitas-galat">Asumsi Normalitas Galat</h4>
<pre><code class="language-{r}">library(tseries)
res&lt;-residuals(anova)
shapiro&lt;-shapiro.test(res)
jarque.bera&lt;-jarque.bera.test(res)
</code></pre>
<blockquote>
<ul>
<li><code>residuals(anova)</code> berfungsi sebagai nilai sisaan dalam model anova  </li>
<li>Uji normalitas dengan <code>shapiro.test(res)</code> dan <code>jarque.bera.test(res)</code> menggunakan nilai sisaan</li>
</ul>
</blockquote>
<pre><code class="language-{r,">shapiro
jarque.bera
</code></pre>
<blockquote>
<p>Karena <em>p-value</em> seluruh uji &gt; 0.05, maka dapat disimpulkan bahwa sisaan berdistribusi Normal.  </p>
</blockquote>
<h3 id="asumsi-homogenitas">Asumsi Homogenitas</h3>
<p>  Asumsi homogenitas berarti mengasumsikan ragam bernilai sama untuk setiap amatan pada faktor sama. Dapat diidentifikasi secara visual menggunakan Plot <em>Scale-Location</em> dan uji homogenitas statistik seperti uji Levene, uji Breusch Pagan, dan uji Bartlett.  </p>
<h4 id="asumsi-homogenitas-dengan-plot-scale-location">Asumsi Homogenitas dengan Plot <em>Scale-Location</em></h4>
<pre><code class="language-{r}">plot(anova, 3)
</code></pre>
<blockquote>
<p>Plot yang ditampilkan dari plot dengan tipe 3 adalah plot Scale Location.  </p>
</blockquote>
<p>Dari plot, di garis bagian awal membentuk garis yang tidak terlalu horizontal, sedangkan sisanya membentuk garis horizontal. Asumsi homogenitas terpenuhi jika garis yang terbentuk adalah garis horizontal. Untuk memastikannya, perlu diuji lebih lanjut.  </p>
<h4 id="asumsi-homogenitas-dengan-statistik-uji">Asumsi Homogenitas dengan statistik uji</h4>
<pre><code class="language-{r}">library(car)
levene&lt;-leveneTest(data$`Denyut Jantung`~data$Bising*data$Temp)
bartlett1&lt;-bartlett.test(data$`Denyut Jantung`~data$Bising)
bartlett2&lt;-bartlett.test(data$`Denyut Jantung`~data$Temp)
</code></pre>
<blockquote>
<ul>
<li>Uji Levene menguji homogenitas ragam dengan interaksi  </li>
<li>Uji Bartlett menguji homogenitas ragam untuk setiap faktor</li>
</ul>
</blockquote>
<pre><code class="language-{r,">library(knitr)
df&lt;-data.frame(Uji=c(&quot;Levene&quot;, rep(&quot;Bartlett&quot;, 2)), Perlakuan=c(&quot;Interaksi&quot;, &quot;Tingkat Kebisingan&quot;, &quot;Temperatur&quot;), Nilai_Statistik=c(levene[1,2], bartlett1$statistic, bartlett2$statistic), p_value=c(levene[1,3], bartlett1$p.value, bartlett2$p.value))
kable(df, caption = &quot;Uji Homogenitas&quot;)
</code></pre>
<blockquote>
<p>Karena <em>p-value</em> seluruh uji &gt; 0.05, maka dapat disimpulkan bahwa data memiliki ragam yang homogen, baik dari setiap faktor maupun dari interaksi.  </p>
</blockquote>
<p>Asumsi Normalitas dan asumsi Homogenitas terpenuhi, sehingga analisis ragam dapat dilakukan.  </p>
<h2 id="analisis-data">Analisis Data</h2>
<h3 id="tabel-anova">TABEL ANOVA</h3>
<p>Hipotesis  </p>
<ul>
<li>Hipotesis untuk faktor tingkat kebisingan:<br>$H_0:$ $\alpha_1=$ $\alpha_2=0$<br>$H_1:$ sekurang-kurangnya satu $\alpha_i$ tidak sama dengan 0  </li>
<li>Hipotesis untuk faktor temperatur:<br>$H_0:$ $\beta_1=$ $\beta_2=0$<br>$H_1:$ sekurang-kurangnya satu $\beta_j$ tidak sama dengan 0  </li>
<li>Hipotesis untuk interaksi:<br>$H_0:$ $(\alpha\beta)<em>{11}=$ $(\alpha\beta)</em>{12}=$ $(\alpha\beta)<em>{21}=$ $(\alpha\beta)</em>{22}=0$<br>$H_1:$ sekurang-kurangnya satu $(\alpha\beta)_{ij}$ tidak sama dengan 0</li>
</ul>
<p>Dari sebelumnya, model aov() telah disimpan dalam objek anova.  </p>
<pre><code class="language-{r}">summary(anova)
</code></pre>
<blockquote>
<p><code>summary(anova)</code> menampilkan hasil perhitungan seperti Df(derajat bebas), Sum Sq(Jumlah Kuadrat), Mean Sq(Kuadrat Tengah), F value($F_{hit}$), dan Pr(&gt;F)(p-value)  </p>
</blockquote>
<p>Nilai p dari Faktor Tingkat Kebisingan bernilai &lt;0.05, sehingga tolak $H_0$ yang berarti terdapat perbedaan rata-rata yang nyata antar level dalam Faktor Tingkat Kebisingan.  </p>
<p>Nilai p dari Faktor Temperatur bernilai &lt;0.05, sehingga tolak $H_0$ yang berarti terdapat perbedaan rata-rata yang nyata antar level dalam Faktor Temperatur. </p>
<p>Nilai p dari Faktor Interaksi bernilai &gt;0.05, sehingga terima $H_0$ yang berarti tidak terdapat interaksi antara Faktor Tingkat Kebisingan dengan Faktor Temperatur.  </p>
<h3 id="uji-lanjut-perbandingan-berganda">Uji Lanjut Perbandingan Berganda</h3>
<p>Karena kedua faktor masing-masing hanya memiliki 2 level, maka sebenarnya tidak diperlukan uji lanjut perbandingan berganda. Namun, tak jadi masalah jika ingin dilakukan untuk membuktikan bahwa kedua faktor memiliki perbedaan yang nyata.  </p>
<h4 id="uji-bnj-tukeys-hsd">Uji BNJ (Tukey&#39;s HSD)</h4>
<pre><code class="language-{r}">TukeyHSD(anova)
</code></pre>
<blockquote>
<p>Menggunakan <code>TukeyHSD()</code> dengan argumen model anova untuk menampilkan hasil perbandingan uji berganda  </p>
</blockquote>
<p>Hasil output menunjukkan bahwa Denyut Jantung dengan Tingkat Kebisingan B2 (87-88 dB) berbeda dengan B1 (83-84 dB), karena nilai p&lt;0.05. Begitu pula Denyut Jantung dengan Temperatur A2($25^{\circ}$C - $26^{\circ}$C) berbeda dengan A1($29^{\circ}$C - $30^{\circ}$C), karena nilai p&lt;0.05.  </p>
<p>Sedangkan untuk interaksi, Denyut Jantung dengan Interaksi B2:A2 (Tingkat Kebisingan 87-88 dB dan Temperatur $29^{\circ}$C - $30^{\circ}$C) berbeda dengan Interaksi B1:A1 (Tingkat Kebisingan 83-84 dB dan Temperatur $25^{\circ}$C - $26^{\circ}$C), Interaksi B2:A1 (Tingkat Kebisingan 87-88 dB dan Temperatur $25^{\circ}$C - $26^{\circ}$C), dan Interaksi B1:A2 (Tingkat Kebisingan 83-84 dB dan Temperatur $29^{\circ}$C - $30^{\circ}$C). Sedangkan interaksi lainnya tidak berbeda.  </p>
<p>Hasil uji di atas sebanding dengan boxplot yang ditampilkan sebelumnya.  </p>
<h3 id="effect-size">Effect Size</h3>
<pre><code class="language-{r}">library(lsr)
etaSquared(anova)
</code></pre>
<blockquote>
<p>Untuk menghitung eta squared, digunakan function <code>etaSquared()</code> dengan argument model anova  </p>
</blockquote>
<p>Partial eta squared dari faktor bising bernilai 0.355 yang berarti 35.5% respon denyut jantung dapat dijelaskan oleh tingkat kebisingan.  </p>
<p>Partial eta squared dari faktor temperatur bernilai 0.271 yang berarti 27.1% respon denyut jantung dapat dijelaskan oleh temperatur.  </p>
<p>Partial eta squared dari interaksi faktor tingkat kebisingan dan temperatur bernilai 0.038 yang berarti hanya 3.8% respon denyut jantung dapat dijelaskan oleh interaksi faktor.  </p>
<h2 id="uji-beda-rata-rata-2-faktor">Uji Beda Rata-Rata 2 Faktor</h2>
<h3 id="rata-rata-denyut-jantung-dengan-2-level-tingkat-kebisingan">Rata-Rata Denyut Jantung dengan 2 Level Tingkat Kebisingan</h3>
<p>B1=83-84 dB<br>B2=87-88 dB  </p>
<p>Hipotesis:<br>$H_0: \mu_{B1}=\mu_{B2}$<br>$H_1: \mu_{B1}&lt;\mu_{B2}$  </p>
<pre><code class="language-{r,">library(dplyr)
library(knitr)
data_B1&lt;-filter(data, Bising==&quot;B1&quot;)[,c(1,3)]
data_B2&lt;-filter(data, Bising==&quot;B2&quot;)[,c(1,3)]
df_B&lt;-data.frame(B1=data_B1$`Denyut Jantung`, B2=data_B2$`Denyut Jantung`)
kable(df_B, caption = &quot;Denyut Jantung&quot;)
</code></pre>
<pre><code class="language-{r}">t.test(x=df_B$B1, y=df_B$B2, alternative = &quot;less&quot;, paired = F, var.equal = T)
</code></pre>
<blockquote>
<p><code>t.test()</code> untuk menghitung statistik uji t dengan argument 2 sampel, yaitu x dan y, hipotesis alternatif kurang dari, data tidak berpasangan, dan ragam dianggap sama  </p>
</blockquote>
<p>Karena <em>p-value</em>&lt;0.05, maka tolak $H_0$, yang berarti terdapat cukup bukti untuk menyatakan bahwa denyut jantung operator yang bekerja di tempat dengan tingkat kebisingan 87-88 dB lebih tinggi dibandingkan dengan yang bekerja di tempat dengan tingkat kebisingan 83-84 dB  </p>
<h3 id="rata-rata-denyut-jantung-dengan-2-level-temperatur">Rata-Rata Denyut Jantung dengan 2 Level Temperatur</h3>
<p>A1=$25^{\circ}$C - $26^{\circ}$C<br>A2=$29^{\circ}$C - $30^{\circ}$C</p>
<p>Hipotesis:<br>$H_0: \mu_{A1}=\mu_{A2}$<br>$H_1: \mu_{A1}&lt;\mu_{A2}$  </p>
<pre><code class="language-{r,">library(dplyr)
library(knitr)
data_A1&lt;-filter(data, Temp==&quot;A1&quot;)[,c(1,3)]
data_A2&lt;-filter(data, Temp==&quot;A2&quot;)[,c(1,3)]
df_A&lt;-data.frame(A1=data_A1$`Denyut Jantung`, A2=data_A2$`Denyut Jantung`)
kable(df_A, caption = &quot;Denyut Jantung&quot;)
</code></pre>
<pre><code class="language-{r}">t.test(x=df_A$A1, y=df_A$A2, alternative = &quot;less&quot;, paired = F, var.equal = T)
</code></pre>
<p>Karena <em>p-value</em>&lt;0.05, maka tolak $H_0$, yang berarti terdapat cukup bukti untuk menyatakan bahwa denyut jantung operator yang bekerja di tempat dengan temperatur $25^{\circ}$C - $26^{\circ}$C lebih tinggi dibandingkan dengan yang bekerja di tempat dengan temperatur $29^{\circ}$C - $30^{\circ}$C  </p>
<h1 id="perhitungan-manual">PERHITUNGAN MANUAL</h1>
<p>Perhitungan manual berikut adalah perhitungan untuk ANOVA (menghitung Jumlah Kuadrat, Derajat Bebas, Kuadrat Tengah, dan $F_{hit}$)  </p>
<h2 id="derajat-bebas">Derajat Bebas</h2>
<pre><code class="language-{r}">N&lt;- nrow(data)
r&lt;- length(unique(data$Bising))
c&lt;- length(unique(data$Temp))
n&lt;- N/(r*c)
DB_Bising&lt;-r-1
DB_Temp&lt;-c-1
DB_Int&lt;-DB_Bising*DB_Temp
DBG&lt;-r*c*(n-1)
DBT&lt;-(r*c*n)-1
</code></pre>
<blockquote>
<p>Keterangan<br>N=rcn=banyaknya pengamatan<br>r=banyaknya level pada Faktor Tingkat Kebisingan<br>c=banyaknya level pada Faktor Temperature<br>n=banyaknya ulangan per level Faktor Tingkat Kebisingan dan Faktor Temperatur  </p>
</blockquote>
<pre><code class="language-{r}">N; r; c; n
</code></pre>
<pre><code class="language-{r}">DB_Bising; DB_Temp; DB_Int; DBG; DBT
</code></pre>
<h2 id="jumlah-kuadrat">Jumlah Kuadrat</h2>
<p>$JKT=\sum_{i=1}^{2}\sum_{j=1}^{2}\sum_{k=1}^{10}x_{ijk}^2-{FK}$<br>$JK_{Bising}=\frac{\sum_{i=1}^{2}{x_{i..}^2}}{cn}-{FK}$<br>$JK_{Temp}=\frac{\sum_{j=1}^{2}{x_{.j.}^2}}{rn}-{FK}$<br>$JK_{Int}=\frac{\sum_{i=1}^{2}\sum_{j=1}^{2}{x_{ij.}^2}}{n}-{FK}-JK_{Bising}-JK_{Temp}$<br>$JKG=JKT-JK_{Bising}-JK_{Temp}-JK_{Int}$<br>dengan<br>$FK (Faktor Koreksi)=\frac{x_{...}^2}{rcn}$  </p>
<pre><code class="language-{r}">FK&lt;-(sum(data$`Denyut Jantung`))^2/(r*c*n)
JKT&lt;-sum(data$`Denyut Jantung`^2) - FK

bising.sum&lt;-aggregate(`Denyut Jantung` ~ Bising , data, sum )[,2]
bising.square&lt;-sum(bising.sum^2)
JK_Bising&lt;-bising.square/(c*n) - FK

temp.sum&lt;-aggregate(`Denyut Jantung` ~ Temp , data, sum )[,2]
temp.square&lt;-sum(temp.sum^2)
JK_Temp&lt;-temp.square/(r*n) - FK

inter.sum&lt;-aggregate(`Denyut Jantung` ~ Temp + Bising, data, sum)[,3]
inter.square&lt;-sum(inter.sum^2)
JK_Int&lt;-inter.square/n - FK - JK_Bising - JK_Temp

JKG&lt;-JKT - JK_Bising - JK_Temp - JK_Int
</code></pre>
<pre><code class="language-{r}">JK_Bising; JK_Temp; JK_Int; JKG; JKT
</code></pre>
<h2 id="kuadrat-tengah">Kuadrat Tengah</h2>
<pre><code class="language-{r}">KT_Bising&lt;-JK_Bising/DB_Bising
KT_Temp&lt;-JK_Temp/DB_Temp
KT_Int&lt;-JK_Int/DB_Int
KTG&lt;-JKG/DBG
</code></pre>
<pre><code class="language-{r}">KT_Bising; KT_Temp; KT_Int; KTG
</code></pre>
<h2 id="statistik-f-dan-p-value">Statistik F dan <em>p-value</em></h2>
<pre><code class="language-{r}">F_Bising&lt;-KT_Bising/KTG
F_Temp&lt;-KT_Temp/KTG
F_Int&lt;-KT_Int/KTG

pval_Bising&lt;-pf(F_Bising, DB_Bising, DBG, lower.tail = F)
pval_Temp&lt;-pf(F_Temp, DB_Temp, DBG, lower.tail = F)
pval_Int&lt;-pf(F_Int, DB_Int, DBG, lower.tail = F)
</code></pre>
<pre><code class="language-{r}">F_Bising; F_Temp; F_Int
pval_Bising; pval_Temp; pval_Int
</code></pre>
<h2 id="tabel-anova-manual">TABEL ANOVA (MANUAL)</h2>
<pre><code class="language-{r,">library(knitr)
tabel_anova&lt;-data.frame(SK=c(&quot;Bising&quot;, &quot;Temp&quot;, &quot;Bising:Temp&quot;, &quot;Galat&quot;, &quot;Total&quot;), DB=c(DB_Bising, DB_Temp, DB_Int, DBG, DBT), 
JK=c(JK_Bising, JK_Temp, JK_Int, JKG, JKT),
KT=c(KT_Bising, round(KT_Temp,3), round(KT_Int,3), round(KTG,3), &quot;NA&quot;),
Fhit=c(round(F_Bising,3), round(F_Temp,3), round(F_Int,3), &quot;NA&quot;, &quot;NA&quot;),
p_value=c(round(pval_Bising,3), round(pval_Temp,3), round(pval_Int,3), &quot;NA&quot;, &quot;NA&quot;))
kable(tabel_anova, caption=&quot;Tabel ANOVA&quot;)
</code></pre>
<p><strong>Hasil perhitungan manual sama dengan hasil menggunakan function</strong>  </p>
<h2 id="effect-size-manual">Effect Size (MANUAL)</h2>
<p>$$
\eta^2_{partial}=\frac{JK_{Faktor}}{JK_{Faktor}+JKG}
$$  </p>
<pre><code class="language-{r}">eta.sqr.part_Bising&lt;-JK_Bising/(JK_Bising+JKG)
eta.sqr.part_Temp&lt;-JK_Temp/(JK_Temp+JKG)
eta.sqr.part_Int&lt;-JK_Int/(JK_Int+JKG)
</code></pre>
<pre><code class="language-{r,">library(knitr)
eta_sq&lt;-data.frame(Faktor=c(&quot;Tingkat Kebisingan&quot;, &quot;Temperatur&quot;, &quot;Interaksi&quot;), Partial_Eta_Squared=c(eta.sqr.part_Bising, eta.sqr.part_Temp, eta.sqr.part_Int))
kable(eta_sq)
</code></pre>
<p><strong>Hasil perhitungan manual sama dengan hasil menggunakan function</strong>  </p>
<h2 id="uji-beda-rata-rata-2-faktor-1">Uji Beda Rata-Rata 2 Faktor</h2>
<h3 id="rata-rata-denyut-jantung-dengan-2-level-tingkat-kebisingan-1">Rata-Rata Denyut Jantung dengan 2 Level Tingkat Kebisingan</h3>
<p>B1=83-84 dB<br>B2=87-88 dB  </p>
<p>Hipotesis:<br>$H_0: \mu_{B1}=\mu_{B2}$<br>$H_1: \mu_{B1}&lt;\mu_{B2}$  </p>
<pre><code class="language-{r}">mean.B1&lt;-mean(data_B1$`Denyut Jantung`)
mean.B2&lt;-mean(data_B2$`Denyut Jantung`)
var.B1&lt;-var(data_B1$`Denyut Jantung`)
var.B2&lt;-var(data_B2$`Denyut Jantung`)
n.B1&lt;-length(data_B1$`Denyut Jantung`)
n.B2&lt;-length(data_B2$`Denyut Jantung`)
s2_p.B&lt;-(var.B1*(n.B1-1)+var.B2*(n.B2-1))/(n.B1+n.B2-2)
thit.B&lt;-(mean.B1-mean.B2)/(sqrt(s2_p.B*(1/n.B1+1/n.B2)))
p_value.B&lt;-pt(thit.B, df=(n.B1+n.B2-2))
</code></pre>
<pre><code class="language-{r}">mean.B1; mean.B2
thit.B
p_value.B
</code></pre>
<h3 id="rata-rata-denyut-jantung-dengan-2-level-temperatur-1">Rata-Rata Denyut Jantung dengan 2 Level Temperatur</h3>
<p>A1=$25^{\circ}$C - $26^{\circ}$C<br>A2=$29^{\circ}$C - $30^{\circ}$C</p>
<p>Hipotesis:<br>$H_0: \mu_{A1}=\mu_{A2}$<br>$H_1: \mu_{A1}&lt;\mu_{A2}$  </p>
<pre><code class="language-{r}">mean.A1&lt;-mean(data_A1$`Denyut Jantung`)
mean.A2&lt;-mean(data_A2$`Denyut Jantung`)
var.A1&lt;-var(data_A1$`Denyut Jantung`)
var.A2&lt;-var(data_A2$`Denyut Jantung`)
n.A1&lt;-length(data_A1$`Denyut Jantung`)
n.A2&lt;-length(data_A2$`Denyut Jantung`)
s2_p.A&lt;-(var.A1*(n.A1-1)+var.A2*(n.A2-1))/(n.A1+n.A2-2)
thit.A&lt;-(mean.A1-mean.A2)/(sqrt(s2_p.A*(1/n.A1+1/n.A2)))
p_value.A&lt;-pt(thit.A, df=(n.A1+n.A2-2))
</code></pre>
<pre><code class="language-{r}">mean.A1; mean.A2
thit.A
p_value.A
</code></pre>
<p><strong>Hasil perhitungan manual sama dengan hasil menggunakan function</strong>  </p>
<h1 id="hasil-dan-pembahasan">HASIL DAN PEMBAHASAN</h1>
<h2 id="tabel-anova-1">Tabel ANOVA</h2>
<p>Setelah dianalisis menggunakan Anova 2 arah dengan interaksi, hasil uji menunjukkan bahwa Tingkat Kebisingan dan Temperatur berpengaruh secara signifikan terhadap Denyut Jantung. Namun, Tingkat Kebisingan dan Temperatur tidak memiliki interaksi dalam memengaruhi Denyut Jantung operator. Hal tersebut ditunjukkan dengan nilai <em>p-value</em> dari Faktor Tingkat Kebisingan dan Faktor Temperatur yang sangat kecil. Sedangkan <em>p-value</em> dari interaksi bernilai sangat besar.  </p>
<h2 id="kontribusi-faktor-terhadap-denyut-jantung">Kontribusi Faktor Terhadap Denyut Jantung</h2>
<p>Faktor Tingkat Kebisingan berkontribusi sebesar 35.5% dan Faktor Temperatur berkontribusi sebesar 27.1% dalam menjelaskan Denyut Jantung operator. Faktor interaksi hanya berkontribusi sebesar 3.8% dalam menjelaskan Denyut Jantung operator. Sedangkan kontribusi sisanya dijelaskan oleh faktor-faktor yang tidak diteliti dalam penelitian ini.  </p>
<h2 id="boxplot-dan-rata-rata-denyut-jantung">Boxplot dan Rata-Rata Denyut Jantung</h2>
<p>Dari boxplot, terlihat bahwa rata-rata denyut jantung operator yang bekerja di tingkat kebisingan 87-88 dB lebih tinggi dibandingkan dengan operator yang bekerja di tingkat kebisingan 83-84 dB. Begitu pula untuk yang temperatur, di mana rata-rata denyut jantung operator yang bekerja di ruang dengan temperatur $29^{\circ}$C - $30^{\circ}$C lebih tinggi dibandingkan dengan operator yang bekerja di ruang dengan temperatur $25^{\circ}$C - $26^{\circ}$C. Secara deskriptif, rata-rata denyut jantung dapat dilihat di tabel berikut:  </p>
<table>
<thead>
<tr>
<th>Level</th>
<th>Rata-rata denyut jantung</th>
</tr>
</thead>
<tbody><tr>
<td>83-84 dB</td>
<td>78.85</td>
</tr>
<tr>
<td>87-88 dB</td>
<td>83.35</td>
</tr>
</tbody></table>
<p>Table: Tingkat Kebisingan  </p>
<table>
<thead>
<tr>
<th>Level</th>
<th>Rata-rata denyut jantung</th>
</tr>
</thead>
<tbody><tr>
<td>$25^{\circ}$C - $26^{\circ}$C</td>
<td>79.25</td>
</tr>
<tr>
<td>$29^{\circ}$C - $30^{\circ}$C</td>
<td>82.95</td>
</tr>
</tbody></table>
<p>Table: Temperatur  </p>
<p>Untuk menguji bahwa:  </p>
<ul>
<li>rata-rata denyut jantung operator yang bekerja di tingkat kebisingan 87-88 dB lebih tinggi dibandingkan dengan operator yang bekerja di tingkat kebisingan 83-84 dB</li>
<li>rata-rata denyut jantung operator yang bekerja di ruang dengan temperatur $29^{\circ}$C - $30^{\circ}$C lebih tinggi dibandingkan dengan operator yang bekerja di ruang dengan temperatur $25^{\circ}$C - $26^{\circ}$C.</li>
</ul>
<p>maka dilakukan uji beda rata-rata 2 populasi. Didapatkan hasil keduanya dengan nilai <em>p-value</em> sangat kecil, sehingga dapat disimpulkan bahwa rata-rata denyut jantung operator yang bekerja di ruang dengan tingkat kebisingan 87-88 dB lebih tinggi dibandingkan dengan operator yang bekerja di tingkat kebisingan 83-84 dB, serta rata-rata denyut jantung operator yang bekerja di ruang dengan temperatur $29^{\circ}$C - $30^{\circ}$C lebih tinggi dibandingkan dengan operator yang bekerja di ruang dengan temperatur $25^{\circ}$C - $26^{\circ}$C. </p>
<blockquote>
<p><em>Jadi, semakin tinggi tingkat kebisingan dan temperatur di suatu ruangan, maka denyut jantung akan semakin meningkat.</em>  </p>
</blockquote>
<h1 id="daftar-pustaka">DAFTAR PUSTAKA</h1>
<p>Pramana dkk. <em>DASAR-DASAR STATISTIKA Dengan Software R</em>. 2019. Jakarta: Penerbit IN MEDIA  </p>
<p>Walpole, Ronald E. <em>PENGANTAR STATISTIKA</em>. 1993. Jakarta: Penerbit PT Gramedia Pustaka Utama  </p>
<p>Walpole, Ronald E &amp; Raymond H. Myers. <em>Ilmu Peluang dan Statistika untuk Insinyur dan Ilmuwan</em>. 1995. Bandung: Penerbit ITB Bandung  </p>
<p>Yitnosumarto, Suntoyo. <em>PERCOBAAN: Perancangan, Analisis, dan Interpretasinya</em>. 1993. Jakarta: Penerbit PT Gramedia Pustaka Utama  </p>
<p><a href="http://www.sthda.com/english/wiki/two-way-anova-test-in-r">www.sthda.com/english/wiki/two-way-anova-test-in-r</a>, Mei 2022  </p>
<p><a href="https://www.statology.org/eta-squared/">www.statology.org/eta-squared/</a>, Mei 2022  </p>
<p><a href="https://digilib.uns.ac.id/dokumen/download/7463/MTk4MzU=/Analisis-pengaruh-temperatur-dan-kebisingan-terhadap-kerja-sistem-cardiovascular-operator-produksi-Studi-Kasus-PT-General-Electric-Lighting-Indonesia-abstrak.pdf">digilab.uns.ac.id</a>  </p>
