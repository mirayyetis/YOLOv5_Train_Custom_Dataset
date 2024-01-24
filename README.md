# YOLOv5_Train_Custom_Dataset
## Training custom dataset with YOLOv5

 Model eğitimi yapmak istiyorsanız ilk olarak veri toplamanız gerekmektedir. Daha sonra topladığınız bu görselleri **Roboflow** üzerinden etiketlemeniz gerekmektedir. Örnek bir dataset yukarıdaki dataset dosyasında yer almaktadır. Örnek bir dataset de bıraktım deneyebilmeniz için **sag_right-roboflow** adında.

YOLOv5 algoritmasını kullanarak cmd üzerinden model eğitimi yapmak istiyorsanız şu adımları yapmanız gerekmektedir :

1) yolov5-master klasörünü bilgisayarınıza indirip zip’ten çıkartın.
2) yolov5-master içerisinde yer alan **data** klasörüne oluşturduğunuz veri setini yükleyin. (ama verileriniz benim yüklemiş olduğum **ilerisol_deneme**klasöründeki düzende olmalıdır!)
3) Bir **data yaml** dosyası oluşturmamız gerekmektedir. **coco128 yaml** dosyasını kopyalayıp **custom_data** adında bir yaml dosyası kendiniz için oluşturmalısınız. Burada ilgili *pathleri* düzenlemeniz gerekmektedir. Birde roboflowda etiketlediğiniz verilere atadığınız etiketleri yazmanız gerekmektedir. *(Örneğin ben ileri sol tabelası etiketlemiştim ve etiket numarasını 6 olarak belirlemiştim buna göre yaml dosyamı düzenledim)*
4) Eğitim kısmında **train.py** kodu kullanılmaktadır. 
5) **cmd** üzerinden yolov5-master klasörünüz içerisine girmelisiniz. Bu klasörün içerisindeyken şu komutu çalıştırmanız gerekmektedir :
**``` python train.py --img 416 --batch 32 --epochs 100 --data custom_data.yaml --weights yolov5s.pt –cache ```**
Eğitiminiz başlayacaktır. *(burada yer alan img, batch ve epoch değerlerini değiştirebilirsiniz)*. Eğitim tamamlanınca yolov5-master klasörünüz içerisindeki **runs** klasörünün içerisine gittiğinizde **best.pt** dosyası ile karşılaşacaksınız bu oluşturmuş olduğunuz modeldir.
 6) Eğer eğitim sırasında kütüphanelerin sürümlerinden kaynaklı hata alıyorsanız eğer klasörde de yer alan **requirements.tx**t dosyasının içerisinde yer alan sürümleri yüklemeniz gerekmektdir. Bunun içinde cmd üzerinden yolov5-master klasörünüz içerisine girip şu komutu başlatmalısınız : 
**```python -m pip install -r requirements.txt ```**

7) Oluşturduğunuz modeli bilgisayar kameranız ile test etmek istiyorsanız **yolov5_real_time.py** kodunun içerisine best.pt dosyanızın yolunu ilgili yere yerleştirdikten sonra kodu çalıştırarak görebilrisiniz.

