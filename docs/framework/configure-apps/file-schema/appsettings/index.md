---
title: アプリ設定スキーマ
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: d02f9f952c0ca7651d27571111a2d29f3d1130fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921297"
---
# <a name="app-settings-schema"></a><span data-ttu-id="e7093-102">アプリ設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="e7093-102">App Settings schema</span></span>

<span data-ttu-id="e7093-103">ファイル パス、XML Web サービス URL、またはアプリケーションのその他のカスタム構成情報など、カスタム アプリケーションの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7093-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="e7093-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="e7093-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="e7093-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="e7093-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="e7093-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<add>** ](add-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="e7093-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md) </span></span>  
<span data-ttu-id="e7093-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clear>** ](clear-element-for-appsettings.md) </span><span class="sxs-lookup"><span data-stu-id="e7093-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md) </span></span>  
<span data-ttu-id="e7093-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<remove>** ](remove-element-for-appsettings.md)</span><span class="sxs-lookup"><span data-stu-id="e7093-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)</span></span>

| <span data-ttu-id="e7093-109">要素</span><span class="sxs-lookup"><span data-stu-id="e7093-109">Element</span></span> | <span data-ttu-id="e7093-110">説明</span><span class="sxs-lookup"><span data-stu-id="e7093-110">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="e7093-111"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="e7093-111">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="e7093-112">アプリケーションの設定を制御する **\<add>** 、 **\<clear>** 、 **\<remove>** のタグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e7093-112">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="e7093-113">省略可能な **file** 属性があります。</span><span class="sxs-lookup"><span data-stu-id="e7093-113">Has an optional **file** attribute.</span></span> |
| [<span data-ttu-id="e7093-114"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="e7093-114">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="e7093-115">設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e7093-115">Defines a setting.</span></span> <span data-ttu-id="e7093-116">**\<appSettings>** の子です。</span><span class="sxs-lookup"><span data-stu-id="e7093-116">Child of **\<appSettings>**.</span></span> <span data-ttu-id="e7093-117">**key** 属性と **value** 属性が必要です。</span><span class="sxs-lookup"><span data-stu-id="e7093-117">Requires **key** and **value** attributes.</span></span> |
| [<span data-ttu-id="e7093-118"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="e7093-118">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="e7093-119">すべての設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="e7093-119">Clears all settings.</span></span> <span data-ttu-id="e7093-120">**\<appSettings>** の子です。</span><span class="sxs-lookup"><span data-stu-id="e7093-120">Child of **\<appSettings>**.</span></span> <span data-ttu-id="e7093-121">属性はありません。</span><span class="sxs-lookup"><span data-stu-id="e7093-121">Has no attributes.</span></span> |
| [<span data-ttu-id="e7093-122"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="e7093-122">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="e7093-123">設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="e7093-123">Removes a setting.</span></span> <span data-ttu-id="e7093-124">**\<appSettings>** の子です。</span><span class="sxs-lookup"><span data-stu-id="e7093-124">Child of **\<appSettings>**.</span></span> <span data-ttu-id="e7093-125">**key** 属性が必要です。</span><span class="sxs-lookup"><span data-stu-id="e7093-125">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="e7093-126">\<appSettings> 要素</span><span class="sxs-lookup"><span data-stu-id="e7093-126">\<appSettings> element</span></span>

<span data-ttu-id="e7093-127">この要素には、アプリケーションの設定を制御する **\<add>** 、 **\<clear>** 、 **\<remove>** のタグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e7093-127">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="e7093-128">**file** の省略可能な属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="e7093-128">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="e7093-129">\<add> 要素</span><span class="sxs-lookup"><span data-stu-id="e7093-129">\<add> element</span></span>

<span data-ttu-id="e7093-130">カスタム アプリケーション設定を名前/値のペアとしてアプリケーション設定コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="e7093-130">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="e7093-131">**key** および **value** の属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="e7093-131">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="e7093-132">\<clear> 要素</span><span class="sxs-lookup"><span data-stu-id="e7093-132">\<clear> element</span></span>

<span data-ttu-id="e7093-133">継承したカスタム アプリケーション設定へのすべての参照を削除し、 **\<clear>** 要素の後の **\<add>** 要素によって追加された参照のみを許可します。</span><span class="sxs-lookup"><span data-stu-id="e7093-133">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="e7093-134">属性は定義されません。</span><span class="sxs-lookup"><span data-stu-id="e7093-134">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="e7093-135">\<remove> 要素</span><span class="sxs-lookup"><span data-stu-id="e7093-135">\<remove> element</span></span>

<span data-ttu-id="e7093-136">アプリケーション設定コレクションから継承したカスタム アプリケーション設定への参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="e7093-136">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="e7093-137">**key** の属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="e7093-137">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="e7093-138">例</span><span class="sxs-lookup"><span data-stu-id="e7093-138">Example</span></span>

<span data-ttu-id="e7093-139">次の例は、カスタム アプリケーション設定を定義する外部アプリケーション設定ファイル (*custom.config*) を示しています。</span><span class="sxs-lookup"><span data-stu-id="e7093-139">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="e7093-140">次の例は、外部設定ファイルで設定を使用して、独自のアプリケーション設定を設定するアプリケーション構成ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="e7093-140">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="e7093-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7093-141">See also</span></span>

- [<span data-ttu-id="e7093-142">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="e7093-142">Application Settings Overview</span></span>](../../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="e7093-143">アプリケーション設定アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="e7093-143">Application Settings Architecture</span></span>](../../../winforms/advanced/application-settings-architecture.md)
