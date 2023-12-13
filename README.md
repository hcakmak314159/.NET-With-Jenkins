# My .NET App with Jenkins CI/CD

![.NET Logo](https://upload.wikimedia.org/wikipedia/commons/e/ee/.NET_Core_Logo.svg)

Bu proje, .NET ile geliştirilmiş bir uygulamayı Jenkins ile sürekli entegrasyon ve sürekli dağıtım (CI/CD) süreçleriyle yönetmeyi amaçlamaktadır.

## Proje Yapısı

- `Jenkinsfile`: Jenkins CI/CD iş akışını tanımlayan dosya.
- `JenkinsApp/`: .NET uygulamasının kaynak kodları.
- `Dockerfile`: Docker imajını oluşturan dosya.

## Jenkins CI/CD Özellikleri

- Jenkins, GitHub ile entegre edilmiştir.
- Her GitHub push işlemi, Jenkins tarafından algılanır.
- Jenkins, Docker kullanarak uygulamayı derler ve dağıtır.
- Jenkins Blue Ocean arayüzü kullanılmıştır.

## Nasıl Başlatılır?

1. Projeyi klonlayın: `git clone https://github.com/your-username/your-repo.git`
2. Jenkinsfile'ı Jenkins CI/CD iş akışınıza uygun olarak özelleştirin.
3. Jenkins üzerinde yeni bir iş (job) oluşturun ve bu repo ile bağlayın.

## Lisans

Bu proje MIT lisansı altında lisanslanmıştır. Detaylar için [LICENSE](LICENSE) dosyasına bakınız.
