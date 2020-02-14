---
title: セキュリティ透過コード、レベル 2
ms.date: 03/30/2017
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
ms.openlocfilehash: 7ac5660c2c431505f4992f5e687974c2b9d06672
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216994"
---
# <a name="security-transparent-code-level-2"></a><span data-ttu-id="af6b0-102">セキュリティ透過コード、レベル 2</span><span class="sxs-lookup"><span data-stu-id="af6b0-102">Security-Transparent Code, Level 2</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="af6b0-103">レベル2の透過性は .NET Framework 4 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="af6b0-103">Level 2 transparency was introduced in the .NET Framework 4.</span></span> <span data-ttu-id="af6b0-104">このモデルには、透過的なコード、セキュリティ セーフ クリティカル コード、およびセキュリティ クリティカル コードの 3 つの基本思想があります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-104">The three tenets of this model are transparent code, security-safe-critical code, and security-critical code.</span></span>

- <span data-ttu-id="af6b0-105">透過的なコード (完全に信頼されて実行されているコードを含む) は、他の透過的なコードまたはセキュリティ セーフ クリティカル コードのみを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-105">Transparent code, including code that is running as full trust, can call other transparent code or security-safe-critical code only.</span></span> <span data-ttu-id="af6b0-106">また、ドメインの部分信頼アクセス許可セット (存在する場合) で許可されるアクションのみを実行できます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-106">It can only perform actions allowed by the domain’s partial trust permission set (if one exists).</span></span> <span data-ttu-id="af6b0-107">透過的なコードでは、次のアクションは実行できません。</span><span class="sxs-lookup"><span data-stu-id="af6b0-107">Transparent code cannot do the following:</span></span>

  - <span data-ttu-id="af6b0-108">特権の <xref:System.Security.CodeAccessPermission.Assert%2A> または昇格を実行する。</span><span class="sxs-lookup"><span data-stu-id="af6b0-108">Perform an <xref:System.Security.CodeAccessPermission.Assert%2A> or elevation of privilege.</span></span>

  - <span data-ttu-id="af6b0-109">アンセーフ コードまたは検証不可能なコードを含める。</span><span class="sxs-lookup"><span data-stu-id="af6b0-109">Contain unsafe or unverifiable code.</span></span>

  - <span data-ttu-id="af6b0-110">クリティカル コードを直接呼び出す。</span><span class="sxs-lookup"><span data-stu-id="af6b0-110">Directly call critical code.</span></span>

  - <span data-ttu-id="af6b0-111">ネイティブ コードまたは <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 属性を持つコードを呼び出す。</span><span class="sxs-lookup"><span data-stu-id="af6b0-111">Call native code or code with the <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.</span></span>

  - <span data-ttu-id="af6b0-112"><xref:System.Security.Permissions.SecurityAction.LinkDemand> によって保護されているメンバーを呼び出す。</span><span class="sxs-lookup"><span data-stu-id="af6b0-112">Call a member that is protected by a <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span></span>

  - <span data-ttu-id="af6b0-113">クリティカルな型を継承する。</span><span class="sxs-lookup"><span data-stu-id="af6b0-113">Inherit from critical types.</span></span>

  <span data-ttu-id="af6b0-114">また、透過的メソッドでは、クリティカルな仮想メソッドをオーバーライドしたりクリティカルなインターフェイス メソッドを実装したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="af6b0-114">In addition, transparent methods cannot override critical virtual methods or implement critical interface methods.</span></span>

- <span data-ttu-id="af6b0-115">セーフ クリティカル コードは完全に信頼されていますが、透過的なコードから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-115">Safe-critical code is fully trusted but is callable by transparent code.</span></span> <span data-ttu-id="af6b0-116">また、完全に信頼されたコードのうち限られた領域のみを公開します。正確性とセキュリティの検証はセーフ クリティカル コード内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-116">It exposes a limited surface area of full-trust code; correctness and security verifications happen in safe-critical code.</span></span>

- <span data-ttu-id="af6b0-117">セキュリティ クリティカル コードは任意のコードを呼び出すことができ、完全に信頼されていますが、透過的なコードから呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="af6b0-117">Security-critical code can call any code and is fully trusted, but it cannot be called by transparent code.</span></span>

## <a name="usage-examples-and-behaviors"></a><span data-ttu-id="af6b0-118">使用例と動作</span><span class="sxs-lookup"><span data-stu-id="af6b0-118">Usage Examples and Behaviors</span></span>

<span data-ttu-id="af6b0-119">.NET Framework 4 つの規則 (レベル2の透過性) を指定するには、アセンブリに次の注釈を使用します。</span><span class="sxs-lookup"><span data-stu-id="af6b0-119">To specify .NET Framework 4 rules (level 2 transparency), use the following annotation for an assembly:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level2)]
```

<span data-ttu-id="af6b0-120">.NET Framework 2.0 のルール (レベル 1 の透過性) にロックするには、次の注釈に使用します。</span><span class="sxs-lookup"><span data-stu-id="af6b0-120">To lock into the .NET Framework 2.0 rules (level 1 transparency), use the following annotation:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level1)]
```

<span data-ttu-id="af6b0-121">アセンブリに注釈を設定しない場合は、既定で .NET Framework 4 ルールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-121">If you do not annotate an assembly, the .NET Framework 4 rules are used by default.</span></span> <span data-ttu-id="af6b0-122">ただし、推奨されるベストプラクティスは、既定に応じてではなく、<xref:System.Security.SecurityRulesAttribute> 属性を使用することです。</span><span class="sxs-lookup"><span data-stu-id="af6b0-122">However, the recommended best practice is to use the <xref:System.Security.SecurityRulesAttribute> attribute instead of depending on the default.</span></span>

### <a name="assembly-wide-annotation"></a><span data-ttu-id="af6b0-123">アセンブリ全体の注釈</span><span class="sxs-lookup"><span data-stu-id="af6b0-123">Assembly-wide Annotation</span></span>

<span data-ttu-id="af6b0-124">アセンブリ レベルでの属性の使用には、次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-124">The following rules apply to the use of attributes at the assembly level:</span></span>

- <span data-ttu-id="af6b0-125">属性なし: 属性を指定しない場合は、ランタイムによってすべてのコードがセキュリティ クリティカルとして解釈されます。ただし、セキュリティ クリティカルであると継承規則に違反する場合 (たとえば、透過的な仮想メソッドまたはインターフェイス メソッドをオーバーライドまたは実装する場合) は除きます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-125">No attributes: If you do not specify any attributes, the runtime interprets all code as security-critical, except where being security-critical violates an inheritance rule (for example, when overriding or implementing a transparent virtual or interface method).</span></span> <span data-ttu-id="af6b0-126">そのような場合、メソッドはセーフ クリティカルになります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-126">In those cases, the methods are safe-critical.</span></span> <span data-ttu-id="af6b0-127">属性を指定しない場合、透過性規則は共通言語ランタイムによって自動的に判断されます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-127">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span>

- <span data-ttu-id="af6b0-128">`SecurityTransparent`: すべてのコードが透過的になります。アセンブリ全体で特権の必要な操作や安全でない操作は実行されません。</span><span class="sxs-lookup"><span data-stu-id="af6b0-128">`SecurityTransparent`: All code is transparent; the entire assembly will not do anything privileged or unsafe.</span></span>

- <span data-ttu-id="af6b0-129">`SecurityCritical`: このアセンブリ内の型によって導入されるすべてのコードはクリティカルになり、その他のすべてのコードは透過的になります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-129">`SecurityCritical`: All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="af6b0-130">このシナリオは属性を指定しない場合に似ていますが、共通言語ランタイムによって透過性規則が自動的に判断されることはありません。</span><span class="sxs-lookup"><span data-stu-id="af6b0-130">This scenario is similar to not specifying any attributes; however, the common language runtime does not automatically determine the transparency rules.</span></span> <span data-ttu-id="af6b0-131">たとえば、仮想メソッドまたは抽象メソッドをオーバーライドしたり、インターフェイス メソッドを実装したりする場合、既定では、そのメソッドは透過的になります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-131">For example, if you override a virtual or abstract method or implement an interface method, by default, that method is transparent.</span></span> <span data-ttu-id="af6b0-132">そのメソッドには `SecurityCritical` または `SecuritySafeCritical` の注釈を明示的に付ける必要があります。そうしないと、読み込み時に <xref:System.TypeLoadException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-132">You must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`; otherwise, a <xref:System.TypeLoadException> will be thrown at load time.</span></span> <span data-ttu-id="af6b0-133">この規則は、基底クラスと派生クラスの両方が同じアセンブリ内にある場合にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-133">This rule also applies when both the base class and the derived class are in the same assembly.</span></span>

- <span data-ttu-id="af6b0-134">`AllowPartiallyTrustedCallers` (レベル 2 のみ): すべてのコードが既定で透過的になります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-134">`AllowPartiallyTrustedCallers` (level 2 only): All code defaults to transparent.</span></span> <span data-ttu-id="af6b0-135">ただし、個々の型やメンバーに他の属性を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-135">However, individual types and members can have other attributes.</span></span>

<span data-ttu-id="af6b0-136">次の表は、レベル2のアセンブリレベルの動作とレベル1を比較したものです。</span><span class="sxs-lookup"><span data-stu-id="af6b0-136">The following table compares the assembly level behavior for Level 2 with Level 1.</span></span>

|<span data-ttu-id="af6b0-137">Assembly 属性</span><span class="sxs-lookup"><span data-stu-id="af6b0-137">Assembly attribute</span></span>|<span data-ttu-id="af6b0-138">[レベル 2]</span><span class="sxs-lookup"><span data-stu-id="af6b0-138">Level 2</span></span>|<span data-ttu-id="af6b0-139">[レベル 1]</span><span class="sxs-lookup"><span data-stu-id="af6b0-139">Level 1</span></span>|
|------------------------|-------------|-------------|
|<span data-ttu-id="af6b0-140">部分的に信頼されたアセンブリで属性なし</span><span class="sxs-lookup"><span data-stu-id="af6b0-140">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="af6b0-141">型およびメンバーは既定で透過的になりますが、セキュリティ クリティカルまたはセキュリティ セーフ クリティカルにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-141">Types and members are by default transparent, but can be security-critical or security-safe-critical.</span></span>|<span data-ttu-id="af6b0-142">すべての型およびメンバーは透過的です。</span><span class="sxs-lookup"><span data-stu-id="af6b0-142">All types and members are transparent.</span></span>|
|<span data-ttu-id="af6b0-143">属性なし</span><span class="sxs-lookup"><span data-stu-id="af6b0-143">No attribute</span></span>|<span data-ttu-id="af6b0-144">属性を指定しない場合、透過性規則は共通言語ランタイムによって自動的に判断されます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-144">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span> <span data-ttu-id="af6b0-145">すべての型およびメンバーはセキュリティ クリティカルになります (ただし、セキュリティ クリティカルになると継承ルールに違反する場所を除く)。</span><span class="sxs-lookup"><span data-stu-id="af6b0-145">All types and members are security-critical, except where being security-critical violates an inheritance rule.</span></span>|<span data-ttu-id="af6b0-146">完全に信頼されたアセンブリ (グローバル アセンブリ キャッシュ内に存在するか、`AppDomain` で完全に信頼と指定されている) では、すべての型は透過的であり、すべてのメンバーはセキュリティ セーフ クリティカルです。</span><span class="sxs-lookup"><span data-stu-id="af6b0-146">On a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`) all types are transparent and all members are security-safe-critical.</span></span>|
|`SecurityTransparent`|<span data-ttu-id="af6b0-147">すべての型およびメンバーは透過的です。</span><span class="sxs-lookup"><span data-stu-id="af6b0-147">All types and members are transparent.</span></span>|<span data-ttu-id="af6b0-148">すべての型およびメンバーは透過的です。</span><span class="sxs-lookup"><span data-stu-id="af6b0-148">All types and members are transparent.</span></span>|
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="af6b0-149">該当しない。</span><span class="sxs-lookup"><span data-stu-id="af6b0-149">Not applicable.</span></span>|<span data-ttu-id="af6b0-150">すべての型およびメンバーはセキュリティ クリティカルです。</span><span class="sxs-lookup"><span data-stu-id="af6b0-150">All types and members are security-critical.</span></span>|
|`SecurityCritical`|<span data-ttu-id="af6b0-151">このアセンブリ内の型によって導入されるすべてのコードはクリティカルになり、その他のすべてのコードは透過的になります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-151">All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="af6b0-152">仮想メソッドまたは抽象メソッドをオーバーライドしたり、インターフェイス メソッドを実装したりする場合は、メソッドに `SecurityCritical` または `SecuritySafeCritical` の注釈を明示的に付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-152">If you override a virtual or abstract method or implement an interface method, you must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`.</span></span>|<span data-ttu-id="af6b0-153">すべてのコードは既定で透過的になります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-153">All code defaults to transparent.</span></span> <span data-ttu-id="af6b0-154">ただし、個々の型やメンバーに他の属性を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-154">However, individual types and members can have other attributes.</span></span>|

### <a name="type-and-member-annotation"></a><span data-ttu-id="af6b0-155">型およびメンバーの注釈</span><span class="sxs-lookup"><span data-stu-id="af6b0-155">Type and Member Annotation</span></span>

<span data-ttu-id="af6b0-156">型に適用されるセキュリティ属性は、その型によって導入されるメンバーにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-156">The security attributes that are applied to a type also apply to the members that are introduced by the type.</span></span> <span data-ttu-id="af6b0-157">ただし、基底クラスまたはインターフェイスの実装の仮想オーバーライドや抽象オーバーライドには適用されません。</span><span class="sxs-lookup"><span data-stu-id="af6b0-157">However, they do not apply to virtual or abstract overrides of the base class or interface implementations.</span></span> <span data-ttu-id="af6b0-158">型およびメンバーのレベルでの属性の使用には、次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-158">The following rules apply to the use of attributes at the type and member level:</span></span>

- <span data-ttu-id="af6b0-159">`SecurityCritical`: 型またはメンバーはクリティカルで、完全に信頼されているコードからのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-159">`SecurityCritical`: The type or member is critical and can be called only by full-trust code.</span></span> <span data-ttu-id="af6b0-160">セキュリティ クリティカルな型で導入されるメソッドはクリティカルです。</span><span class="sxs-lookup"><span data-stu-id="af6b0-160">Methods that are introduced in a security-critical type are critical.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="af6b0-161">基底クラスまたはインターフェイスで導入されてセキュリティ クリティカルなクラスでオーバーライドまたは実装される仮想メソッドおよび抽象メソッドは、既定では透過的です。</span><span class="sxs-lookup"><span data-stu-id="af6b0-161">Virtual and abstract methods that are introduced in base classes or interfaces, and overridden or implemented in a security-critical class are transparent by default.</span></span> <span data-ttu-id="af6b0-162">これらのメソッドは、`SecuritySafeCritical` または `SecurityCritical` のいずれかとして指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-162">They must be identified as either `SecuritySafeCritical` or `SecurityCritical`.</span></span>

- <span data-ttu-id="af6b0-163">`SecuritySafeCritical`: 型またはメンバーはセーフ クリティカルです。</span><span class="sxs-lookup"><span data-stu-id="af6b0-163">`SecuritySafeCritical`: The type or member is safe-critical.</span></span> <span data-ttu-id="af6b0-164">ただし、型またはメンバーは透過的な (部分的に信頼された) コードから呼び出すことができ、機能的に他のクリティカル コードと同等になります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-164">However, the type or member can be called from transparent (partially trusted) code and is as capable as any other critical code.</span></span> <span data-ttu-id="af6b0-165">コードはセキュリティ監査を受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-165">The code must be audited for security.</span></span>

## <a name="override-patterns"></a><span data-ttu-id="af6b0-166">オーバーライドのパターン</span><span class="sxs-lookup"><span data-stu-id="af6b0-166">Override Patterns</span></span>

<span data-ttu-id="af6b0-167">レベル 2 の透過性で使用できるメソッドのオーバーライドを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="af6b0-167">The following table shows the method overrides allowed for level 2 transparency.</span></span>

|<span data-ttu-id="af6b0-168">基底クラスの仮想/インターフェイス メンバー</span><span class="sxs-lookup"><span data-stu-id="af6b0-168">Base virtual/interface member</span></span>|<span data-ttu-id="af6b0-169">オーバーライド/インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af6b0-169">Override/interface</span></span>|
|------------------------------------|-------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

## <a name="inheritance-rules"></a><span data-ttu-id="af6b0-170">継承規則</span><span class="sxs-lookup"><span data-stu-id="af6b0-170">Inheritance Rules</span></span>

<span data-ttu-id="af6b0-171">このセクションでは、アクセスおよび機能に基づいて、次の順序が `Transparent`、`Critical`、および `SafeCritical` のコードに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="af6b0-171">In this section, the following order is assigned to `Transparent`, `Critical`, and `SafeCritical` code based on access and capabilities:</span></span>

`Transparent` < `SafeCritical` < `Critical`

- <span data-ttu-id="af6b0-172">型の規則: 左から右に向かってアクセス制限がより厳しくなります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-172">Rules for types: Going from left to right, access becomes more restrictive.</span></span> <span data-ttu-id="af6b0-173">派生型は、基本型と少なくとも同じ程度に制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-173">Derived types must be at least as restrictive as the base type.</span></span>

- <span data-ttu-id="af6b0-174">メソッドの規則。基底メソッドのアクセシビリティを派生メソッドで変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="af6b0-174">Rules for methods: Derived methods cannot change accessibility from the base method.</span></span> <span data-ttu-id="af6b0-175">既定の動作では、注釈のない派生メソッドはすべて `Transparent` になります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-175">For default behavior, all derived methods that are not annotated are `Transparent`.</span></span> <span data-ttu-id="af6b0-176">クリティカルな型の派生型では、オーバーライドしたメソッドに `SecurityCritical` の注釈が明示的に付けられていない場合に、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-176">Derivatives of critical types cause an exception to be thrown if the overridden method is not explicitly annotated as `SecurityCritical`.</span></span>

<span data-ttu-id="af6b0-177">次の表に、使用できる型の継承パターンを示します。</span><span class="sxs-lookup"><span data-stu-id="af6b0-177">The following table shows the allowed type inheritance patterns.</span></span>

|<span data-ttu-id="af6b0-178">[基底クラス]</span><span class="sxs-lookup"><span data-stu-id="af6b0-178">Base class</span></span>|<span data-ttu-id="af6b0-179">派生クラスで可能なレベル</span><span class="sxs-lookup"><span data-stu-id="af6b0-179">Derived class can be</span></span>|
|----------------|--------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`Transparent`|`Critical`|
|`SafeCritical`|`SafeCritical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Critical`|

<span data-ttu-id="af6b0-180">次の表に、使用できない型の継承パターンを示します。</span><span class="sxs-lookup"><span data-stu-id="af6b0-180">The following table shows the disallowed type inheritance patterns.</span></span>

|<span data-ttu-id="af6b0-181">[基底クラス]</span><span class="sxs-lookup"><span data-stu-id="af6b0-181">Base class</span></span>|<span data-ttu-id="af6b0-182">派生クラスで不可のレベル</span><span class="sxs-lookup"><span data-stu-id="af6b0-182">Derived class cannot be</span></span>|
|----------------|-----------------------------|
|`SafeCritical`|`Transparent`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

<span data-ttu-id="af6b0-183">次の表に、使用できるメソッドの継承パターンを示します。</span><span class="sxs-lookup"><span data-stu-id="af6b0-183">The following table shows the allowed method inheritance patterns.</span></span>

|<span data-ttu-id="af6b0-184">基底メソッド</span><span class="sxs-lookup"><span data-stu-id="af6b0-184">Base method</span></span>|<span data-ttu-id="af6b0-185">派生メソッドで可能なレベル</span><span class="sxs-lookup"><span data-stu-id="af6b0-185">Derived method can be</span></span>|
|-----------------|---------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

<span data-ttu-id="af6b0-186">次の表に、使用できないメソッドの継承パターンを示します。</span><span class="sxs-lookup"><span data-stu-id="af6b0-186">The following table shows the disallowed method inheritance patterns.</span></span>

|<span data-ttu-id="af6b0-187">基底メソッド</span><span class="sxs-lookup"><span data-stu-id="af6b0-187">Base method</span></span>|<span data-ttu-id="af6b0-188">派生メソッドで不可のレベル</span><span class="sxs-lookup"><span data-stu-id="af6b0-188">Derived method cannot be</span></span>|
|-----------------|------------------------------|
|`Transparent`|`Critical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

> [!NOTE]
> <span data-ttu-id="af6b0-189">これらの継承規則は、レベル 2 の型およびメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-189">These inheritance rules apply to level 2 types and members.</span></span> <span data-ttu-id="af6b0-190">レベル 1 アセンブリ内の型は、レベル 2 のセキュリティ クリティカルな型およびメンバーから継承できます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-190">Types in level 1 assemblies can inherit from level 2 security-critical types and members.</span></span> <span data-ttu-id="af6b0-191">したがって、レベル 2 の型およびメンバーでは、レベル 1 の継承先に対して個別の継承確認要求が必要です。</span><span class="sxs-lookup"><span data-stu-id="af6b0-191">Therefore, level 2 types and members must have separate inheritance demands for level 1 inheritors.</span></span>

## <a name="additional-information-and-rules"></a><span data-ttu-id="af6b0-192">追加情報と規則</span><span class="sxs-lookup"><span data-stu-id="af6b0-192">Additional Information and Rules</span></span>

### <a name="linkdemand-support"></a><span data-ttu-id="af6b0-193">LinkDemand のサポート</span><span class="sxs-lookup"><span data-stu-id="af6b0-193">LinkDemand Support</span></span>

<span data-ttu-id="af6b0-194">レベル 2 の透過性モデルでは、<xref:System.Security.Permissions.SecurityAction.LinkDemand> は <xref:System.Security.SecurityCriticalAttribute> 属性に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-194">The level 2 transparency model replaces the <xref:System.Security.Permissions.SecurityAction.LinkDemand> with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="af6b0-195">レガシ (レベル 1) コードでは、<xref:System.Security.Permissions.SecurityAction.LinkDemand> は自動的 <xref:System.Security.Permissions.SecurityAction.Demand> として扱われます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-195">In legacy (level 1) code, a <xref:System.Security.Permissions.SecurityAction.LinkDemand> is automatically treated as a <xref:System.Security.Permissions.SecurityAction.Demand>.</span></span>

### <a name="reflection"></a><span data-ttu-id="af6b0-196">リフレクション</span><span class="sxs-lookup"><span data-stu-id="af6b0-196">Reflection</span></span>

<span data-ttu-id="af6b0-197">クリティカル メソッドを呼び出したりクリティカル フィールドを読み取ったりすると、完全信頼の確認要求がトリガーされます (プライベート メソッドまたはプライベート フィールドを呼び出す場合と同様)。</span><span class="sxs-lookup"><span data-stu-id="af6b0-197">Invoking a critical method or reading a critical field triggers a demand for full trust (just as if you were invoking a private method or field).</span></span> <span data-ttu-id="af6b0-198">したがって、完全に信頼されているコードではクリティカル メソッドを呼び出すことができるのに対し、部分的に信頼されたコードでは呼び出すことができません。</span><span class="sxs-lookup"><span data-stu-id="af6b0-198">Therefore, full-trust code can invoke a critical method, whereas partial-trust code cannot.</span></span>

<span data-ttu-id="af6b0-199"><xref:System.Reflection> 名前空間に追加された `SecurityCritical`、`SecuritySafeCritical`、および `SecurityTransparent` の各プロパティを使用すると、型、メソッド、またはフィールドが <xref:System.Type.IsSecurityCritical%2A>、<xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>、または <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A> のどれであるかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="af6b0-199">The following properties have been added to the <xref:System.Reflection> namespace to determine whether the type, method, or field is `SecurityCritical`, `SecuritySafeCritical`, or `SecurityTransparent`:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, and <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span></span> <span data-ttu-id="af6b0-200">属性の存在を確認する代わりに、リフレクションを使用して透過性を判断するには、これらのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="af6b0-200">Use these properties to determine transparency by using reflection instead of checking for the presence of the attribute.</span></span> <span data-ttu-id="af6b0-201">透過性の規則は複雑なので、属性のチェックでは不十分なことがあります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-201">The transparency rules are complex, and checking for the attribute may not be sufficient.</span></span>

> [!NOTE]
> <span data-ttu-id="af6b0-202">`SafeCritical` メソッドは、<xref:System.Type.IsSecurityCritical%2A> と <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>の両方に対して `true` を返します。これは、`SafeCritical` は実際には重要です (クリティカルコードと同じ機能を持ちますが、透過的なコードから呼び出すことができます)。</span><span class="sxs-lookup"><span data-stu-id="af6b0-202">A `SafeCritical` method returns `true` for both <xref:System.Type.IsSecurityCritical%2A> and <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, because `SafeCritical` is indeed critical (it has the same capabilities as critical code, but it can be called from transparent code).</span></span>

<span data-ttu-id="af6b0-203">動的メソッドは、関連付けられているモジュールの透過性を継承します。型の透過性は継承しません (型に関連付けられている場合)。</span><span class="sxs-lookup"><span data-stu-id="af6b0-203">Dynamic methods inherit the transparency of the modules they are attached to; they do not inherit the transparency of the type (if they are attached to a type).</span></span>

### <a name="skip-verification-in-full-trust"></a><span data-ttu-id="af6b0-204">完全な信頼での検証のスキップ</span><span class="sxs-lookup"><span data-stu-id="af6b0-204">Skip Verification in Full Trust</span></span>

<span data-ttu-id="af6b0-205">完全に信頼されている透過的なアセンブリの検証をスキップするには、<xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> 属性の `true` プロパティを <xref:System.Security.SecurityRulesAttribute> に設定します。</span><span class="sxs-lookup"><span data-stu-id="af6b0-205">You can skip verification for fully trusted transparent assemblies by setting the <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property to `true` in the <xref:System.Security.SecurityRulesAttribute> attribute:</span></span>

`[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`

<span data-ttu-id="af6b0-206"><xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> プロパティは既定では `false` であるため、検証をスキップするにはこのプロパティを `true` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-206">The <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property is `false` by default, so the property must be set to `true` to skip verification.</span></span> <span data-ttu-id="af6b0-207">これをするのは、最適化のためだけにしてください。</span><span class="sxs-lookup"><span data-stu-id="af6b0-207">This should be done for optimization purposes only.</span></span> <span data-ttu-id="af6b0-208">[PEVerify ツール](../tools/peverify-exe-peverify-tool.md)の `transparent` オプションを使用して、アセンブリ内の透過的なコードが検証可能であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af6b0-208">You should ensure that the transparent code in the assembly is verifiable by using the `transparent` option in the [PEVerify tool](../tools/peverify-exe-peverify-tool.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="af6b0-209">参照</span><span class="sxs-lookup"><span data-stu-id="af6b0-209">See also</span></span>

- [<span data-ttu-id="af6b0-210">透過的セキュリティコード、レベル1</span><span class="sxs-lookup"><span data-stu-id="af6b0-210">Security-Transparent Code, Level 1</span></span>](security-transparent-code-level-1.md)
- [<span data-ttu-id="af6b0-211">セキュリティの変更</span><span class="sxs-lookup"><span data-stu-id="af6b0-211">Security Changes</span></span>](../security/security-changes.md)
