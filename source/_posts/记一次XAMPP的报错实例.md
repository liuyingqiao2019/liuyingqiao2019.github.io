---
title: ��һ��XAMPP�ı���ʵ��
date: 2020-02-11 20:36:34
tags: ����
categories: XAMPP
---

# ��һ��XAMPP�ı���ʵ��

�������÷�����������ҳʱ��ʹ�õ���XAMPP�����ڷ��ʷ����������IPʱ��ȴ���������µı���

**_Uncaught error with message ��[db.WindConnection.init] SQLSTATE[HY000]
[1045] Access denied for user ��root��@��localhost�� (using password: YES)��_**

**_The server encountered an internal error and failed to process your
request. Please try again later. If this error is temporary, reloading the
page might resolve the problem.  
If you are able to contact the administrator report this error
message(<http://www.windframework.com/>)_**

���ݴ�������˵��Ȩ�޲���������������������¿���һ�� **phpasmin** ����˺�����

ͼ�п��Կ��� **root** �������˻������붼��������ȨΪ��  
So�����Ҹ��ݰٶȵķ���һ�ٲ���

![2](2.png)

���˷����ֶ����������⣬�����ص�һ���ǨC **Mysql�����޷�����**

![3](3.png)  
���Կ�����ͼ��XAPMM��Mysql�Լ��޷������ұ�һ��ѵĴ�

![4](4.png)

![5](5.png)

## OK,���ڿ�ʼ��һ�γ��ԣ�

��MysqlĿ¼bin�����ҵ�`my.ini`�ļ��ü��±��򿪣�����`[mysqld]`������������һ�д���`innodb_force_recovery
=4`

![6](6.png)

���XAMPP����  
![7](7.png)

## �ڶ��γ��ԣ�

����־����з�����3306�˿ڱ�ռ�ã���Ȼ3306������

![8](8.png)  
���Ҿͻ�һ���˿���  
�޸�MysqlĿ¼��bin�е�`my.ini`�ļ��Ķ˿����£�  
![9](9.png)

˳���޸��� **Ĭ��ip��ַ** ��  
![10](10.png)

������ǲ��У�  
![11](11.png)

10+Сʱ��ȥ�ˣ����˸��ְ취��û������Mysql�������ǣ���ֱ�� **��װXAMPP**  
![13](13.png)

## ���º���ΪXAMPP��Apache�ĳ�ʼ��

��XAMPP��ѡ������  
![14](14.png)  
����`Apache`�Ķ˿�  
![15](15.png)

ȷ���� **��Ȧ** �ĵط���ѡ��`Apache`�ģ����Ļ� **����**
��Ķ˿�ֵ�������ֺ���Ӹ��㼴�ɣ�����סԭ��������ֵ��������ԭ����ֵ�ֱ���80��443

![16](16.png)

Ȼ����XAMPP���ҵ�Apache��confĿ¼��`httpd.conf`�ļ����ü��±��򿪲�����δ���Ķ˿�ǰ�ĵ�һ����ֵ������ĳɸ��ĺ�Ķ˿�ֵ�����������ǽ�80��Ϊ800��Ctrl+S����

![17](17.png)

����confĿ¼���extra���ҵ�`httpd-
ssl.conf`�ļ����ü��±��򿪲�����δ���Ķ˿�ǰ�ĵڶ�����ֵ������ĳɸ��ĺ�Ķ˿�ֵ�����������ǽ�443��Ϊ4430 �� **Ctrl+S** ����

![18](18.png)

���ڻص�XAMPP����� **Apache** �е� **Start** ,����Apache��Mysql��ɫ����ɫ�����;

![19](19.png)



