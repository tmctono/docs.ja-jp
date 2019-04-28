---
title: <useLegacyJit> 要素
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a467599084f01b1a48c95c5e25fb1f869156dffa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673889"
---
# <a name="uselegacyjit-element"></a><span data-ttu-id="2d7fd-102">\<useLegacyJit> 要素</span><span class="sxs-lookup"><span data-stu-id="2d7fd-102">\<useLegacyJit> Element</span></span>

<span data-ttu-id="2d7fd-103">共通言語ランタイムが Just-In-Time コンパイルの従来の 64 ビット JIT コンパイラを使用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
<span data-ttu-id="2d7fd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2d7fd-104">\<configuration></span></span>  
<span data-ttu-id="2d7fd-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="2d7fd-105">\<runtime></span></span>  
<span data-ttu-id="2d7fd-106">\<useLegacyJit ></span><span class="sxs-lookup"><span data-stu-id="2d7fd-106">\<useLegacyJit></span></span>
  
## <a name="syntax"></a><span data-ttu-id="2d7fd-107">構文</span><span class="sxs-lookup"><span data-stu-id="2d7fd-107">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="2d7fd-108">要素名`useLegacyJit`小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-108">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d7fd-109">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2d7fd-109">Attributes and elements</span></span>

<span data-ttu-id="2d7fd-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d7fd-111">属性</span><span class="sxs-lookup"><span data-stu-id="2d7fd-111">Attributes</span></span>  
  
| <span data-ttu-id="2d7fd-112">属性</span><span class="sxs-lookup"><span data-stu-id="2d7fd-112">Attribute</span></span> | <span data-ttu-id="2d7fd-113">説明</span><span class="sxs-lookup"><span data-stu-id="2d7fd-113">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="2d7fd-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-114">Required attribute.</span></span><br><br><span data-ttu-id="2d7fd-115">ランタイムが従来の 64 ビット JIT コンパイラを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-115">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="2d7fd-116">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="2d7fd-116">enabled attribute</span></span>  
  
| <span data-ttu-id="2d7fd-117">[値]</span><span class="sxs-lookup"><span data-stu-id="2d7fd-117">Value</span></span> | <span data-ttu-id="2d7fd-118">説明</span><span class="sxs-lookup"><span data-stu-id="2d7fd-118">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="2d7fd-119">0</span><span class="sxs-lookup"><span data-stu-id="2d7fd-119">0</span></span>     | <span data-ttu-id="2d7fd-120">共通言語ランタイムは、.NET Framework 4.6 および以降のバージョンに含まれる新しい 64 ビット JIT コンパイラを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-120">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="2d7fd-121">1</span><span class="sxs-lookup"><span data-stu-id="2d7fd-121">1</span></span>     | <span data-ttu-id="2d7fd-122">共通言語ランタイムは、古い 64 ビット JIT コンパイラを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-122">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="2d7fd-123">子要素</span><span class="sxs-lookup"><span data-stu-id="2d7fd-123">Child elements</span></span>

<span data-ttu-id="2d7fd-124">なし</span><span class="sxs-lookup"><span data-stu-id="2d7fd-124">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="2d7fd-125">親要素</span><span class="sxs-lookup"><span data-stu-id="2d7fd-125">Parent elements</span></span>  
  
| <span data-ttu-id="2d7fd-126">要素</span><span class="sxs-lookup"><span data-stu-id="2d7fd-126">Element</span></span>         | <span data-ttu-id="2d7fd-127">説明</span><span class="sxs-lookup"><span data-stu-id="2d7fd-127">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="2d7fd-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="2d7fd-129">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-129">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="2d7fd-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="2d7fd-130">Remarks</span></span>  

<span data-ttu-id="2d7fd-131">以降、.NET Framework 4.6 では、共通言語ランタイムを使用して新しい 64 ビット コンパイラの Just-In-Time (JIT) コンパイル既定。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-131">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="2d7fd-132">場合によっては、64 ビット JIT コンパイラの以前のバージョンで JIT コンパイルされたアプリケーション コードからの動作の違いにあります。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-132">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="2d7fd-133">設定して、`enabled`の属性、`<useLegacyJit>`要素`1`、新しい 64 ビット JIT コンパイラを無効にし、代わりに、従来の 64 ビット JIT コンパイラを使用して、アプリをコンパイルすることができます。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-133">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d7fd-134">`<useLegacyJit>`要素が 64 ビット JIT コンパイルのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-134">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="2d7fd-135">32 ビット JIT コンパイラによるコンパイルには影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-135">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="2d7fd-136">構成ファイルの設定を使用する代わりに、その他の 2 つの方法では、従来の 64 ビット JIT コンパイラが有効にできます。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-136">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="2d7fd-137">環境変数の設定</span><span class="sxs-lookup"><span data-stu-id="2d7fd-137">Setting an environment variable</span></span>

  <span data-ttu-id="2d7fd-138">設定、`COMPLUS_useLegacyJit`するか、環境変数`0`(新しい 64 ビット JIT コンパイラを使用) または`1`(以前の 64 ビット JIT コンパイラを使用)。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-138">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="2d7fd-139">環境変数が*グローバル スコープ*マシン上のすべてのアプリケーションで実行に影響を与えることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-139">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="2d7fd-140">かどうか設定をオーバーライドできますでアプリケーション構成ファイルの設定。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-140">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="2d7fd-141">環境変数名は区別されません。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-141">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="2d7fd-142">レジストリ キーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-142">Adding a registry key</span></span>

  <span data-ttu-id="2d7fd-143">追加することで、従来の 64 ビット JIT コンパイラを有効にすることができます、`REG_DWORD`いずれかの値、`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework`または`HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework`レジストリのキー。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-143">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="2d7fd-144">値の名前は`useLegacyJit`します。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-144">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="2d7fd-145">値が 0 の場合は、新しいコンパイラが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-145">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="2d7fd-146">値が 1 の場合は、従来の 64 ビット JIT コンパイラが有効にします。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-146">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="2d7fd-147">レジストリ値の名前は区別されません。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-147">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="2d7fd-148">値を追加、`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework`キー、マシンで実行されているすべてのアプリに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-148">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="2d7fd-149">値を追加、`HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework`キーが現在のユーザーが実行するすべてのアプリに影響します。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-149">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="2d7fd-150">マシンには、複数のユーザー アカウントを構成、現在のユーザーが実行するアプリのみに影響、値が他のユーザーのレジストリ キーを追加しない限り、します。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-150">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="2d7fd-151">追加、`<useLegacyJit>`要素を構成ファイルが存在する場合、レジストリに設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-151">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d7fd-152">例</span><span class="sxs-lookup"><span data-stu-id="2d7fd-152">Example</span></span>  

<span data-ttu-id="2d7fd-153">次の構成ファイルでは、新しい 64 ビット JIT コンパイラでコンパイルを無効にし、代わりに、従来の 64 ビット JIT コンパイラを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d7fd-153">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d7fd-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d7fd-154">See also</span></span>

- [<span data-ttu-id="2d7fd-155">\<ランタイム > 要素</span><span class="sxs-lookup"><span data-stu-id="2d7fd-155">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [<span data-ttu-id="2d7fd-156">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="2d7fd-156">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
- [<span data-ttu-id="2d7fd-157">軽減策:新しい 64 ビット JIT コンパイラ</span><span class="sxs-lookup"><span data-stu-id="2d7fd-157">Mitigation: New 64-bit JIT Compiler</span></span>](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)
