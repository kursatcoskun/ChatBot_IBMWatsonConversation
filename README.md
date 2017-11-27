
IBM Cloud altyapısında bulunan Watson Conversation servisi kullanılarak Android platformunda geliştirilen bir uygulamadır.  

Burada ilk olarak Watson servisimizi oluşturacağız.

Öncelikle IBM Cloud hesabı oluşturmanız gerekmektedir.  

Bunun için aşağıdaki linkteki sayfada "Sign up" butonundan kayıt olmanız gerekmekte.  

https://www.ibm.com/cloud/  

Aşağıdaki link aracılığıyla 6 aylık promo code edinebilirsiniz.  

https://ibm.onthehub.com/WebStore/OfferingDetails.aspx?o=bb3528b7-2b63-e611-9420-b8ca3a5db7a1  

IBM Cloud'un ana ekranında sağ üstte bulunan Catalog kısmına tıklıyoruz.  
[![image](https://i.hizliresim.com/Qp5MOj.png)](https://hizliresim.com/Qp5MOj)   

Gelen sayfada arama kısmına Conversation yazıyoruz ve çıkan tab'a tıklıyoruz. 

Burada sadece servisin ismini değiştiriyoruz.İngilizce karakterler dışında sıkıntı çıkabiliyor o yüzden türkçe karakter kullanmayınız.  

[![image](https://i.hizliresim.com/0GXDJY.png)](https://hizliresim.com/0GXDJY)

Gelen ekranda "Launch Tool" yazan kısma tıklıyoruz.  

[![image](https://i.hizliresim.com/OybMpn.png)](https://hizliresim.com/OybMpn)  

Gelen ekran yukarıdaki gibi olacaktır. Buradan yeni bir workspace yaratmak için CREATE butonuna tıklıyoruz.Workspace'in ismini girdikten sonra tekrar Create ile workspace'imizi oluşturmuş olduk.   

[![image](https://i.hizliresim.com/5G0V65.png)](https://hizliresim.com/5G0V65) 

Burada intents tabındayken create new dedikten sonra;  

intent_name: Merhaba_intent  

user example= Merhaba  

yazıyoruz arttırmak istersek + ile benzerlerini yazabiliriz.(Örn: Selam)  

Done dedikten sonra sağ üstteki tablardan Dialog kısmına geliyoruz.  

Add node'a tıklıyoruz name this node: kısmına selamlasma_node yazabiliriz.  

Enter an intent kısmına ise intent ismimizi yani Merhaba_intent giriyoruz.  

Enter an respond kısmına ise girdiğimiz kelimeye ne cevap vereceğini yazıyoruz buna örnek "Merhaba, nasıl yardımcı olabilirim?" olabilir.  

[![image](https://i.hizliresim.com/XEG4R5.png)](https://hizliresim.com/XEG4R5)

Burada customize'ın yanındaki X işaretine bastığımızda servisimizde kullanıma hazır olmuş bir dialog olacaktır.   

Denemek için ise en sağ üstteki sohbet ikonuna basarak deneyebiliriz.  

[![image](https://i.hizliresim.com/JO92b5.png)](https://hizliresim.com/JO92b5)

Android Studio kısmına geçersek projedeki kodları base alıp oluşturabilirsiniz. Ancak dikkat etmeniz gereken birkaç yer var.  

[![image](https://i.hizliresim.com/MaQJAM.png)](https://hizliresim.com/MaQJAM)


      ConversationService service = new ConversationService(ConversationService.VERSION_DATE_2016_09_20);

       service.setUsernameAndPassword("Your Watson service UserName", "Your watson service PassWord");

       MessageRequest newMessage = new MessageRequest.Builder().inputText(inputmessage).build();

       MessageResponse response = service.message("Your Workspace Id", newMessage).execute();    
       
 Yukarıdaki kod blogunda username ve password değerleri watson conversation servis altında bulacağız ve workspace id içinde workspace kısmında bulacağız.   
 
[![image](https://i.hizliresim.com/4GAly7.png)](https://hizliresim.com/4GAly7)
 
 Yukarıda service credentials tabı altında görülen kullanıcı adı ve şifrenizi koplalayıp ilgili koda eklenmesi gerekiyor.  
 
[![image](https://i.hizliresim.com/d7rbgp.png)](https://hizliresim.com/d7rbgp) 
 
 Burada ise workspace'in sağ üst köşesinde bulunan üç noktaya tıkladıktan sonr view details'a tıklarsanız workspace id yukarıdaki gibi görünecektir.













