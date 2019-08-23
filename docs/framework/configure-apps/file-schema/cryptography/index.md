---
title: 暗号設定スキーマ
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
ms.openlocfilehash: a7964d01905be4e3dd6e8149e5533e9a2cfd9a71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927628"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="b3070-102">暗号設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="b3070-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="b3070-103">暗号設定スキーマには、アルゴリズムの表示名を、暗号化アルゴリズムを実装するクラスに割り当てる方法を指定する要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b3070-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
 [<span data-ttu-id="b3070-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b3070-104">**\<configuration>**</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="b3070-105"> **\<mscorlib>** </span><span class="sxs-lookup"><span data-stu-id="b3070-105">**\<mscorlib>**</span></span>](mscorlib-element-for-cryptography-settings.md)  
  
 [<span data-ttu-id="b3070-106"> **\<cryptographySettings>** </span><span class="sxs-lookup"><span data-stu-id="b3070-106">**\<cryptographySettings>**</span></span>](cryptographysettings-element.md)  
  
 [<span data-ttu-id="b3070-107"> **\<cryptoNameMapping>** </span><span class="sxs-lookup"><span data-stu-id="b3070-107">**\<cryptoNameMapping>**</span></span>](cryptonamemapping-element.md)  
  
 [<span data-ttu-id="b3070-108"> **\<cryptoClasses>** </span><span class="sxs-lookup"><span data-stu-id="b3070-108">**\<cryptoClasses>**</span></span>](cryptoclasses-element.md)  
  
 [<span data-ttu-id="b3070-109"> **\<cryptoClass>** </span><span class="sxs-lookup"><span data-stu-id="b3070-109">**\<cryptoClass>**</span></span>](cryptoclass-element.md)  
  
 [<span data-ttu-id="b3070-110"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="b3070-110">**\<nameEntry>**</span></span>](nameentry-element.md)  
  
 [<span data-ttu-id="b3070-111"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="b3070-111">**\<oidMap>**</span></span>](oidmap-element.md)  
  
 [<span data-ttu-id="b3070-112"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="b3070-112">**\<oidEntry>**</span></span>](oidentry-element.md)  
  
|<span data-ttu-id="b3070-113">要素</span><span class="sxs-lookup"><span data-stu-id="b3070-113">Element</span></span>|<span data-ttu-id="b3070-114">説明</span><span class="sxs-lookup"><span data-stu-id="b3070-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3070-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="b3070-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="b3070-116">**\<nameEntry>** 要素内の表示名へのマッピングを持つ暗号化クラスのリストを含みます。</span><span class="sxs-lookup"><span data-stu-id="b3070-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="b3070-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="b3070-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="b3070-118">**\<nameEntry>** 要素内の表示名へのマッピングを持つ暗号化クラスを含みます。</span><span class="sxs-lookup"><span data-stu-id="b3070-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="b3070-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="b3070-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="b3070-120">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="b3070-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="b3070-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="b3070-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="b3070-122">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="b3070-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="b3070-123"> **\<mscorlib>** 要素、暗号化設定用</span><span class="sxs-lookup"><span data-stu-id="b3070-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="b3070-124">**\<cryptographySettings >** 要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="b3070-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="b3070-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="b3070-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="b3070-126">アルゴリズムの表示名にクラス名をマップして、1 つのクラスが多くの表示名を持つことを許可します。</span><span class="sxs-lookup"><span data-stu-id="b3070-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="b3070-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="b3070-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="b3070-128">ASN.1 オブジェクト識別子 (OID) を表示名にマップします。</span><span class="sxs-lookup"><span data-stu-id="b3070-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="b3070-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="b3070-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="b3070-130">クラスへの ASN.1 OID マッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="b3070-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3070-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3070-131">See also</span></span>

- [<span data-ttu-id="b3070-132">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="b3070-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b3070-133">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="b3070-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
