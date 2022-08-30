---
layout: page
schemadotorg:
  "@context": http://schema.org/
  "@type": CreativeWork
  "genre": TrainingMaterial

  # Course details
  # "name" -> The acronym and extended name of the course, separated by " - "
  # "description" -> Short description of the course
  name: "GTPB/IBB21"
  description: ""

  # Keywords -> Consult EDAM:Topic
  keywords: ""

  # Audience -> Following Elixir-Tess input
  audience:
    [
      "Academia/ Research Institution",
      "Industry",
      "Non-Profit Organisation",
      "Healthcare",
    ]

  # Author info
  author:
    - "@type": Organization
      name: "The Gulbenkian Training Programme in Bioinformatics"
      alternateName: "GTPB"
      sameAs: "gtpb.igc.gulbenkian.pt/bicourses/index.html"

  # predominant type of learning resources
  "learningResourceType": ["presentation", "exercise", "scripts", "handout"]

  # Contributor info
  contributor:
    - "@type": Person
      name: "CO-AUTHOR_1"
    - "@type": Person
      name: "CO-AUTHOR_2"
    - "@type": Person
      name: "CO-AUTHOR_3"

  # License & Language & url
  license: https://creativecommons.org/licenses/by/4.0/
  inLanguage: "en-us"
  url: "https://gtpb.github.io/IBB21/"
---

![](assets/readme_img/IGC_Tower_DSCF7958_ed.webp)

### Course Description and Learning Objectives

This course provides a contact with a set of themes that illustrates the role of Bioinformatics in Biomedical research: tools and data resources, RNA-seq for differential gene expression, genomes and their annotation, genome alignment and variant calling, and single cell RNA-seq. This exposure to a diversity of techniques is then complemented with a daylong session about automation of analytical tasks using scripting in Unix shell and Python. The course content invites IBB students to an encompassing, integrated vision of Bioinformatics approaches in the scope of Open Science, collaborative work, hypothesis generation and testing.

### Detailed Schedule

**Monday, May 2nd**

<a href= "assets/IBB2022_tao.pdf">Introduction to Bioinformatics, Sequence Data, RNA-seq</a>

09h30-11h00: Introduction (Pedro Fernandes)

11h30-12h30: Resources and file formats of Bioinformatics (Jingtao Lilue)

14h00-16h00: RNA-seq analysis with the Linux command line (Jingtao Lilue)

16h30-18h00: Wrap-up (Pedro Fernandes)

---

**Tuesday, May 3rd**

<a href= "assets/IBB2022v3.pdf">Handling sequence data (NGS)</a>

09h30-11h00: Introduction to NGS Data and FASTQ format (Ricardo Leite)

11h30-12h30: Brief overview of Galaxy platform (tools, workflows...) (Ricardo Leite)

14h00-16h00: Assembly of a bacterial genome (Ricardo Leite)

16h30-18h00: Gene Annotation and taxa identification (Ricardo Leite)

---

**Wednesday, May 4th**

<a href= "assets/Variant_Calling_04_05_2022.pdf">Variant calling / Single Cell RNA-seq</a>

09h30-11h00: Principles of Variant Calling (Daniel Sobral)

11h30-12h30: Genome Alignment and Variant Calling (Daniel Sobral)

14h00-16h00: Variant Calling Using Breseq (Daniel Sobral)

16h30-18h00: Discussion of Variant Calling Results (Daniel Sobral)

---

**Thursday May, 5th**

<a href= "assets/Single_Cell_05_05_2022.pdf">Single Cell RNA-seq</a>

09h30-11h00: Principles of Single-Cell RNA-Seq Analysis (Daniel Sobral)

11h30-12h30: Running the seurat basic tutorial (Daniel Sobral)

14h00-16h00: Running the analysis from Póvoa et al. (2021) (Daniel Sobral)

16h30-18h00: Discussion (Daniel Sobral)

---

**Friday, May 6th**

[Using Scripts to Automate Bioinformatics Data Analysis](pages/Introduction.md)

09h30-11h00: Scripting for automation (Gonçalo Leiria)

11h30-12h30: Scripting in bash (Gonçalo Leiria)

14h00-16h00: Scripting in Python (Gonçalo Leiria)

16h30-18h00: Final wrap-up (Pedro Fernandes, Gonçalo Leiria)

### Instructors

- Pedro Fernandes
- Jingtao Lilue
- Ricardo Leite
- Daniel Sobral
- Gonçalo Leiria

---

**Note:** Bioinformatics hands-on training happens regularly at the IGC.
A variety of themes is offered using consistent methods for the design and delivery of training courses. Please check this [website](http://gtpb.igc-gulbenkian.pt").

**Webpage created by [Goncalo Leiria](https://twitter.com/GndLeiria).**

<br/>

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" property="dct:title">Web_course_template</span> by <span xmlns:cc="http://creativecommons.org/ns#" property="cc:attributionName">GTPB</span> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.
