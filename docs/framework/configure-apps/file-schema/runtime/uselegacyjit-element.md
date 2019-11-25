---
title: <useLegacyJit> 要素
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
ms.openlocfilehash: a126b8c0050a8d1fd96a3d090f9b018a9faa07a7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968852"
---
# <a name="uselegacyjit-element"></a><span data-ttu-id="b5be7-102">\<useLegacyJit> 要素</span><span class="sxs-lookup"><span data-stu-id="b5be7-102">\<useLegacyJit> Element</span></span>

<span data-ttu-id="b5be7-103">共通言語ランタイムが Just-In-Time コンパイルの従来の 64 ビット JIT コンパイラを使用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b5be7-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
<span data-ttu-id="b5be7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b5be7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b5be7-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="b5be7-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="b5be7-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<uselegacyjit> >**</span><span class="sxs-lookup"><span data-stu-id="b5be7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<useLegacyJit>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5be7-107">構文</span><span class="sxs-lookup"><span data-stu-id="b5be7-107">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="b5be7-108">`useLegacyJit` 要素名は大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="b5be7-108">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5be7-109">属性と要素</span><span class="sxs-lookup"><span data-stu-id="b5be7-109">Attributes and elements</span></span>

<span data-ttu-id="b5be7-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b5be7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5be7-111">属性</span><span class="sxs-lookup"><span data-stu-id="b5be7-111">Attributes</span></span>  
  
| <span data-ttu-id="b5be7-112">属性</span><span class="sxs-lookup"><span data-stu-id="b5be7-112">Attribute</span></span> | <span data-ttu-id="b5be7-113">説明</span><span class="sxs-lookup"><span data-stu-id="b5be7-113">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="b5be7-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="b5be7-114">Required attribute.</span></span><br><br><span data-ttu-id="b5be7-115">ランタイムがレガシ64ビット JIT コンパイラを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5be7-115">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="b5be7-116">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="b5be7-116">enabled attribute</span></span>  
  
| <span data-ttu-id="b5be7-117">[値]</span><span class="sxs-lookup"><span data-stu-id="b5be7-117">Value</span></span> | <span data-ttu-id="b5be7-118">説明</span><span class="sxs-lookup"><span data-stu-id="b5be7-118">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="b5be7-119">0</span><span class="sxs-lookup"><span data-stu-id="b5be7-119">0</span></span>     | <span data-ttu-id="b5be7-120">共通言語ランタイムは、.NET Framework 4.6 以降のバージョンに含まれる新しい64ビット JIT コンパイラを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5be7-120">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="b5be7-121">1</span><span class="sxs-lookup"><span data-stu-id="b5be7-121">1</span></span>     | <span data-ttu-id="b5be7-122">共通言語ランタイムは、古い64ビット JIT コンパイラを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5be7-122">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="b5be7-123">子要素</span><span class="sxs-lookup"><span data-stu-id="b5be7-123">Child elements</span></span>

<span data-ttu-id="b5be7-124">None</span><span class="sxs-lookup"><span data-stu-id="b5be7-124">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="b5be7-125">親要素</span><span class="sxs-lookup"><span data-stu-id="b5be7-125">Parent elements</span></span>  
  
| <span data-ttu-id="b5be7-126">要素</span><span class="sxs-lookup"><span data-stu-id="b5be7-126">Element</span></span>         | <span data-ttu-id="b5be7-127">説明</span><span class="sxs-lookup"><span data-stu-id="b5be7-127">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="b5be7-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b5be7-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="b5be7-129">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="b5be7-129">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="b5be7-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="b5be7-130">Remarks</span></span>  

<span data-ttu-id="b5be7-131">.NET Framework 4.6 以降、共通言語ランタイムは、Just-in-time (JIT) コンパイルに新しい64ビットコンパイラを既定で使用します。</span><span class="sxs-lookup"><span data-stu-id="b5be7-131">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="b5be7-132">場合によっては、以前のバージョンの64ビット JIT コンパイラによって JIT コンパイルされたアプリケーションコードとの動作が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b5be7-132">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="b5be7-133">`<useLegacyJit>` 要素の `enabled` 属性を `1`に設定することにより、新しい64ビット JIT コンパイラを無効にし、代わりに従来の64ビット JIT コンパイラを使用してアプリをコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="b5be7-133">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b5be7-134">`<useLegacyJit>` 要素は、64ビットの JIT コンパイルのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="b5be7-134">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="b5be7-135">32ビットの JIT コンパイラでのコンパイルは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="b5be7-135">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="b5be7-136">構成ファイルの設定を使用する代わりに、次の2つの方法で従来の64ビット JIT コンパイラを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b5be7-136">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="b5be7-137">環境変数の設定</span><span class="sxs-lookup"><span data-stu-id="b5be7-137">Setting an environment variable</span></span>

  <span data-ttu-id="b5be7-138">`COMPLUS_useLegacyJit` 環境変数を `0` (新しい64ビット JIT コンパイラを使用) または `1` (古い64ビット JIT コンパイラを使用) のいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="b5be7-138">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```env  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="b5be7-139">環境変数には*グローバルスコープ*があります。これは、コンピューター上で実行されるすべてのアプリケーションに影響を与えることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b5be7-139">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="b5be7-140">設定されている場合は、アプリケーション構成ファイルの設定によって上書きできます。</span><span class="sxs-lookup"><span data-stu-id="b5be7-140">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="b5be7-141">環境変数の名前では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="b5be7-141">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="b5be7-142">レジストリキーの追加</span><span class="sxs-lookup"><span data-stu-id="b5be7-142">Adding a registry key</span></span>

  <span data-ttu-id="b5be7-143">レガシ64ビット JIT コンパイラを有効にするには、レジストリの `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` または `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` キーのいずれかに `REG_DWORD` 値を追加します。</span><span class="sxs-lookup"><span data-stu-id="b5be7-143">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="b5be7-144">この値には `useLegacyJit`という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="b5be7-144">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="b5be7-145">値が0の場合は、新しいコンパイラが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b5be7-145">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="b5be7-146">値が1の場合、レガシ64ビット JIT コンパイラが有効になります。</span><span class="sxs-lookup"><span data-stu-id="b5be7-146">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="b5be7-147">レジストリ値の名前では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="b5be7-147">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="b5be7-148">`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` キーに値を追加すると、コンピューター上で実行されているすべてのアプリに影響します。</span><span class="sxs-lookup"><span data-stu-id="b5be7-148">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="b5be7-149">`HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` キーに値を追加すると、現在のユーザーが実行しているすべてのアプリに影響します。</span><span class="sxs-lookup"><span data-stu-id="b5be7-149">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="b5be7-150">コンピューターに複数のユーザーアカウントが構成されている場合、その値が他のユーザーのレジストリキーにも追加されない限り、現在のユーザーが実行しているアプリのみが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="b5be7-150">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="b5be7-151">構成ファイルに `<useLegacyJit>` 要素を追加すると、レジストリ設定が存在する場合はその設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="b5be7-151">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5be7-152">例</span><span class="sxs-lookup"><span data-stu-id="b5be7-152">Example</span></span>  

<span data-ttu-id="b5be7-153">次の構成ファイルは、新しい64ビット JIT コンパイラでのコンパイルを無効にし、代わりに従来の64ビット JIT コンパイラを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5be7-153">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5be7-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5be7-154">See also</span></span>

- [<span data-ttu-id="b5be7-155">\<ランタイム > 要素</span><span class="sxs-lookup"><span data-stu-id="b5be7-155">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="b5be7-156">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="b5be7-156">\<configuration> Element</span></span>](../configuration-element.md)
- [<span data-ttu-id="b5be7-157">軽減策: 新しい 64 ビット JIT コンパイラ</span><span class="sxs-lookup"><span data-stu-id="b5be7-157">Mitigation: New 64-bit JIT Compiler</span></span>](../../../migration-guide/mitigation-new-64-bit-jit-compiler.md)
