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
ms.openlocfilehash: c632a15552c8ba5743aac1309098b7d7ef949bbd
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088007"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="cbbbe-102">暗号設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="cbbbe-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="cbbbe-103">暗号設定スキーマには、アルゴリズムの表示名を、暗号化アルゴリズムを実装するクラスに割り当てる方法を指定する要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cbbbe-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
<span data-ttu-id="cbbbe-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cbbbe-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cbbbe-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cbbbe-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="cbbbe-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings**](cryptographysettings-element.md) ></span><span class="sxs-lookup"><span data-stu-id="cbbbe-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="cbbbe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoNameMapping >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="cbbbe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>\
<span data-ttu-id="cbbbe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**cryptoClasses >** ](cryptoclasses-element.md)</span><span class="sxs-lookup"><span data-stu-id="cbbbe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>\
<span data-ttu-id="cbbbe-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**cryptoClass >** ](cryptoclass-element.md)</span><span class="sxs-lookup"><span data-stu-id="cbbbe-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)</span></span>\
<span data-ttu-id="cbbbe-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<nameEntry >** ](nameentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="cbbbe-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)</span></span>\
<span data-ttu-id="cbbbe-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<oidMap >** ](oidmap-element.md)</span><span class="sxs-lookup"><span data-stu-id="cbbbe-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>\
<span data-ttu-id="cbbbe-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[ **oidEntry >** ](oidentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="cbbbe-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)</span></span>

|<span data-ttu-id="cbbbe-113">要素</span><span class="sxs-lookup"><span data-stu-id="cbbbe-113">Element</span></span>|<span data-ttu-id="cbbbe-114">説明</span><span class="sxs-lookup"><span data-stu-id="cbbbe-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cbbbe-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="cbbbe-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="cbbbe-116">**\<nameEntry>** 要素内の表示名へのマッピングを持つ暗号化クラスのリストを含みます。</span><span class="sxs-lookup"><span data-stu-id="cbbbe-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="cbbbe-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="cbbbe-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="cbbbe-118">**\<nameEntry>** 要素内の表示名へのマッピングを持つ暗号化クラスを含みます。</span><span class="sxs-lookup"><span data-stu-id="cbbbe-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="cbbbe-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="cbbbe-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="cbbbe-120">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="cbbbe-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="cbbbe-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="cbbbe-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="cbbbe-122">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="cbbbe-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="cbbbe-123"> **\<mscorlib>** 要素、暗号化設定用</span><span class="sxs-lookup"><span data-stu-id="cbbbe-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="cbbbe-124">**\<cryptographySettings >** 要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="cbbbe-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="cbbbe-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="cbbbe-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="cbbbe-126">アルゴリズムの表示名にクラス名をマップして、1 つのクラスが多くの表示名を持つことを許可します。</span><span class="sxs-lookup"><span data-stu-id="cbbbe-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="cbbbe-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="cbbbe-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="cbbbe-128">ASN.1 オブジェクト識別子 (OID) を表示名にマップします。</span><span class="sxs-lookup"><span data-stu-id="cbbbe-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="cbbbe-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="cbbbe-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="cbbbe-130">クラスへの ASN.1 OID マッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="cbbbe-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cbbbe-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbbbe-131">See also</span></span>

- [<span data-ttu-id="cbbbe-132">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="cbbbe-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="cbbbe-133">暗号サービス</span><span class="sxs-lookup"><span data-stu-id="cbbbe-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
