# Deep Graphics Encoder for Real-Time Video Makeup Synthesis from Example
<div>
    <h2><a style="width: 20%;margin: 2.5%;" href="https://www.linkedin.com/in/robin-kips" target="_blank">Robin Kips</a><a style="width: 20%;margin: 2.5%;" href="https://www.linkedin.com/in/ruowei-irene-jiang-a1743576/" target="_blank">Ruowei Jiang</a><a style="width: 10%;margin: 2.5%;" href="https://www.linkedin.com/in/sileyeba/" target="_blank">Sileye Ba</a><a style="width: 10%;margin: 2.5%;" href="https://www.linkedin.com/in/edmundp/" target="_blank">Edmund Phung</a><a style="width: 10%;margin: 2.5%;" href="https://www.linkedin.com/in/parhamaarabi/" target="_blank">Parham Aarabi</a><a style="width: 10%;margin: 2.5%;"   href="https://www.linkedin.com/in/pietro-gori-b097bb118/" target="_blank">Pietro Gori</a><a style="width: 10%;margin: 2.5%;" href="https://www.linkedin.com/in/matthieu-perrot-225ab01b/" target="_blank">Matthieu Perrot</a><a style="width: 10%;margin: 2.5%;" href="https://www.linkedin.com/in/isabelle-bloch-b954144/" target="_blank">Isabelle Bloch</a></h2>
</div>


<p align="center">
   <img  style="width: 32%;margin: 2.5%;" width="40%" src="images/loreal_research.png"> <img  style="width: 32%;margin: 2.5%;" width="40%" src="images/modiface_icon.png">  <img  style="width: 12%;margin: 2.5%;" width="40%" src="images/telecom_icon.png">   <img  style="width: 34%;margin: 2.5%;" width="40%" src="images/idp_icon.png">
</p>



![example_style_transfer](images/example_transfer_armani (3).png)


### Abstract:
While makeup virtual-try-on is now widespread, parametrizing a computer graphics rendering engine for synthesizing images of a given cosmetics product remains a challenging task.
In this paper, we introduce an inverse computer graphics method for automatic makeup synthesis from a reference image, by learning a model that maps an example portrait image with makeup to the space of rendering parameters. 
This method can be used by artists to automatically create realistic virtual cosmetics image samples, or by consumers, to virtually try-on a makeup extracted from their favourite reference image.


### Video examples:

<iframe  style="display: block; margin: auto;" width="560" height="315" src="https://www.youtube.com/embed/GmciY9rUMOw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<iframe style="display: block; margin: auto;"  width="560" height="315" src="https://www.youtube.com/embed/0dMrf0yZvUw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Paper:

Paper : [CVPR Workshop proceedings](tbd.com) \
ArXiv : [https://arxiv.org/pdf/2105.06407.pdf) \
Supplementary Materials : [CVPR Workshop supplementary, TBD](tbd.com)
 <div align="center" style="display:flex; margin-bottom:50px; margin-top: 30px;">
    <div style="width:20%;display: inline-block;">    
        <a href="https://arxiv.org/pdf/2105.06407.pdf" target="_blank">
            <img class="layered-paper-big" style="max-height:200px" src="images/ca_gan_paper-page-001.jpg">
        </a>
    </div>
    <div style="width:70%;display: flex; align-items: center; margin-left: 5%;">
        <div style="text-align: left;">
            <span style="font-size:12pt">R. Kips, R. Jiang, S. Ba, A. Phung, P. Aarabi, P. Gori, M. Perrot, I.Bloch</span><br>
            <span style="font-size:12pt">
                <b>Deep Graphics Encoder for Real-Time Video Makeup Synthesis from Example</b>
            </span>
            <br>
            <span style="font-size:12pt">AIM20 (ECCV20 Workshop)</span>
            <span style="font-size:12pt"><a href="https://arxiv.org/abs/2008.10298" target="_blank">[arXiv]</a>&nbsp;<a href="bibtex.txt" target="_blank">[BibTeX]</a>&nbsp;<a href="ca_gan_supplementary.pdf" target="_blank">[Supplementary Materials]</a></span>
        </div>
    </div>
</div>


### Model Architecture:
The training procedure of our CA-GAN model. First (a) the generator G estimates an image from a source image and a target makeup color. Secondly (b) the discriminator D estimates the makeup color, skin color and a real/fake classification from the generated image, used to compute the color regression loss L_color, background consistency loss *L_bg* and adversarial loss *L_adv*, respectively. Thirdly (c), the source image is reconstructed from the generated one using the makeup color as target. The reconstruction is used to compute the cycle consistency loss *L_cycle*.
<!-- ![model_archi](images/mode_pipeline.png =250x) -->
<p align="center">
	<img width="70%" src="images/model_pipeline (6).png"/>
</p>

### Results:

Modification of makeup color along each dimension of the *CIE Lab* color space, using images from our social media dataset.
The color patch on the bottom-right of each image illustrates the target color passed to the model.
Our approach generalizes to lips and eyes images with various makeup textures and facial poses.

![results_lips](images/lips_full_face (1).png)
![results_eye](images/eye_shadow_full_face (1).png)

Our model shows makeup style transfer performances that are equivalent to state of the art models, while obtaining better preservation of the skin color of the source subject.

![results_vs_transfer](images/qualitative_both (2).png)
