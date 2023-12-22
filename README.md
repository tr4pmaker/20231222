# 20231222
The application system enables the http api interface by default and uses the secret parameter method to authenticate the http restful api interface. However, the secret is hard-coded and the default configuration is <035c73f7-bb6b-4889-a715-d9eb2d1925cc>
![image](https://github.com/tr4pmaker/20231222/assets/68382284/1071f373-b8cd-41b6-81de-126b91caa68f)
You can use this default configuration to conduct credential stuffing attacks and call any API interface, which includes sensitive operations such as obtaining server configuration, setting server configuration, shutting down/restarting the server, etc. Example:
Get server configuration information
![image](https://github.com/tr4pmaker/20231222/assets/68382284/3b845023-6bf0-4adc-ad62-7b9eb74a1f63)
Get interface list
![image](https://github.com/tr4pmaker/20231222/assets/68382284/d5137100-42e6-4904-a554-d839a5d27048)
Complete interface document reference link:
https://github.com/ZLMediaKit/ZLMediaKit/wiki/MediaServer%E6%94%AF%E6%8C%81%E7%9A%84HTTP-API

In addition, docker deployment has secret key reset logic. The secret in /opt/media/conf/config.ini will be reset when the container is started, but the logic fails and the configuration does not take effect successfully. The default key 035c73f7-bb6b-4889 is used. still call any interface
![image](https://github.com/tr4pmaker/20231222/assets/68382284/e6472e7e-82b5-45ca-ba6b-b874ed6bba5c)
Redeploy the container
![image](https://github.com/tr4pmaker/20231222/assets/68382284/1019738c-1a1c-4695-807a-5a5cd7fa7861)
Check the config.ini configuration file, the key has been rewritten
![image](https://github.com/tr4pmaker/20231222/assets/68382284/815d2d4e-a167-454e-a4bb-4ac83d6b57e0)
However, using the default configuration 035c73f7-bb6b-4889-a715-d9eb2d1925cc can still call any interface
![image](https://github.com/tr4pmaker/20231222/assets/68382284/8def7629-ca94-4e83-9669-c48e0c8a95df)
