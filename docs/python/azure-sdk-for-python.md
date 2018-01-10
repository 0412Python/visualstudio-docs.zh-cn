---
title: Azure SDK for Python | Microsoft Docs
ms.custom: 
ms.date: 03/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "11"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- azure
ms.openlocfilehash: 647b07e3816551e60e176280199ad5298db53200
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2018
---
# <a name="azure-sdk-for-python"></a>Azure SDK for Python

Azure SDK for Python 使得从运行在 Windows、Mac OSX 和 Linux 上的应用程序中使用和管理 Microsoft Azure 服务更加方便。

## <a name="installation"></a>安装

从 [Python 包索引](https://pypi.python.org/pypi/azure)安装 Azure SDK。

安装**最新稳定版**（支持 Python 2.7 和 3.3 及更高版本），如下所示：

```command
pip install azure
```

还可按照 Azure 文档中的[安装 Python 和 SDK](https://azure.microsoft.com/documentation/articles/python-how-to-install/) 操作。

## <a name="documentation"></a>文档

文档可能位于 [azure-sdk-for-python.readthedocs.org](http://azure-sdk-for-python.readthedocs.org/en/latest/index.html)。

[Azure SDK for Python 开发人员中心](http://azure.microsoft.com/develop/python/)也有大量有用资源，其中包括许多教程，例如：

- 使用 [Django](/azure/app-service-web/web-sites-python-create-deploy-django-app)、[Flask](/azure/app-service-web/web-sites-python-create-deploy-flask-app) 和 [Bottle](/azure/app-service-web/web-sites-python-create-deploy-bottle-app) 创建 Web 应用。
- [Blob 存储](/azure/storage/storage-python-how-to-use-blob-storage)
- [表存储](/azure/storage/storage-python-how-to-use-table-storage)
- [队列存储](/azure/storage/storage-python-how-to-use-queue-storage)
- [DocumentDB](/azure/documentdb/documentdb-python-application)
- [服务总线队列](/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
- [服务总线主题/订阅](/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
- [服务管理](/azure/cloud-services/cloud-services-python-how-to-use-service-management)

对于不使用文档的公共 API，[SDK 的 GitHub 存储库](https://github.com/Azure/azure-sdk-for-python)中的单元测试是很好的信息来源：

- [存储单元测试](https://github.com/Azure/azure-storage-python/tree/master/tests)
- [服务总线单元测试](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)
- [服务管理单元测试](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)
- [资源管理单元测试](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-mgmt/tests)

## <a name="support"></a>支持

SDK 的 Git 存储库位于 [https://github.com/Azure/azure-sdk-for-python](https://github.com/Azure/azure-sdk-for-python)。

如果发现任何问题或对 SDK 用法有任何疑问，请[在存储库中提出问题](https://github.com/Azure/azure-sdk-for-python/issues)。
