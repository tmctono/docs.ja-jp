---
title: '方法: グローバル アセンブリ キャッシュからアセンブリを削除する'
description: グローバル アセンブリ キャッシュ ツール (Gacutil.exe) または Windows インストーラーを使用して、グローバル アセンブリ キャッシュからアセンブリを削除する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- global assembly cache, removing assemblies
- strong-named assemblies, global assembly cache
- removing assemblies from global assembly cache
- deleting assemblies in global assembly cache
- Global Assembly Cache tool
- GAC (global assembly cache), removing assemblies
ms.assetid: acdcc588-b458-436d-876c-726de68244c1
ms.openlocfilehash: e3a596ea6029ded190c33032e96b601de9d4012d
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104768"
---
# <a name="how-to-remove-an-assembly-from-the-global-assembly-cache"></a><span data-ttu-id="e35fb-103">方法: グローバル アセンブリ キャッシュからアセンブリを削除する</span><span class="sxs-lookup"><span data-stu-id="e35fb-103">How to: Remove an Assembly from the Global Assembly Cache</span></span>

<span data-ttu-id="e35fb-104">グローバル アセンブリ キャッシュ (GAC) からアセンブリを削除するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="e35fb-104">There are two ways to remove an assembly from the global assembly cache (GAC):</span></span>

- <span data-ttu-id="e35fb-105">[グローバル アセンブリ キャッシュ ツール (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) を使用する方法。</span><span class="sxs-lookup"><span data-stu-id="e35fb-105">By using the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md).</span></span> <span data-ttu-id="e35fb-106">このオプションを使用すると、開発およびテスト時に GAC に配置したアセンブリをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e35fb-106">You can use this option to uninstall assemblies that you've placed in the GAC during development and testing.</span></span>

- <span data-ttu-id="e35fb-107">[Windows インストーラー](/windows/desktop/Msi/windows-installer-portal)を使用する方法。</span><span class="sxs-lookup"><span data-stu-id="e35fb-107">By using [Windows Installer](/windows/desktop/Msi/windows-installer-portal).</span></span> <span data-ttu-id="e35fb-108">インストール パッケージをテストするとき、そして実稼働システムのために、アセンブリをアンインストールするにはこのオプションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35fb-108">You should use this option to uninstall assemblies when testing installation packages and for production systems.</span></span>

## <a name="removing-an-assembly-with-gacutilexe"></a><span data-ttu-id="e35fb-109">Gacutil.exe によるアセンブリの削除</span><span class="sxs-lookup"><span data-stu-id="e35fb-109">Removing an assembly with Gacutil.exe</span></span>

<span data-ttu-id="e35fb-110">コマンド プロンプトに次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e35fb-110">At the command prompt, type the following command:</span></span>

<span data-ttu-id="e35fb-111">**gacutil –u** \<*assembly name*></span><span class="sxs-lookup"><span data-stu-id="e35fb-111">**gacutil –u** \<*assembly name*></span></span>

<span data-ttu-id="e35fb-112">このコマンドで、*assembly name* はグローバル アセンブリ キャッシュから削除するアセンブリの名前です。</span><span class="sxs-lookup"><span data-stu-id="e35fb-112">In this command, *assembly name* is the name of the assembly to remove from the global assembly cache.</span></span>

> [!WARNING]
> <span data-ttu-id="e35fb-113">アセンブリが一部のアプリケーションで引き続き必要となる可能性があるので、Gacutil.exe を使用して実稼働システムのアセンブリを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="e35fb-113">You should not use Gacutil.exe to remove assemblies on production systems because of the possibility that the assembly may still be required by some application.</span></span> <span data-ttu-id="e35fb-114">代わりに、GAC にインストールされる各アセンブリの参照カウントを保持する Windows インストーラーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e35fb-114">Instead, you should use the Windows Installer, which maintains a reference count for each assembly it installs in the GAC.</span></span>

<span data-ttu-id="e35fb-115">次の例では、`hello.dll` という名前のアセンブリが、グローバル アセンブリ キャッシュから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e35fb-115">The following example removes an assembly named `hello.dll` from the global assembly cache:</span></span>

```console
gacutil -u hello
```

## <a name="removing-an-assembly-with-windows-installer"></a><span data-ttu-id="e35fb-116">Windows インストーラーでアセンブリを削除する</span><span class="sxs-lookup"><span data-stu-id="e35fb-116">Removing an assembly with Windows Installer</span></span>

<span data-ttu-id="e35fb-117">**コントロール パネル**の**プログラムと機能**アプリで、アンインストールするアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="e35fb-117">From the **Programs and Features** app in **Control Panel**, select the app that you want to uninstall.</span></span> <span data-ttu-id="e35fb-118">インストール パッケージが GAC にアセンブリを配置した場合、それらが別のアプリケーションによって使用されないときは、Windows インストーラーはそれらを削除します。</span><span class="sxs-lookup"><span data-stu-id="e35fb-118">If the installation package placed assemblies in the GAC, Windows Installer will remove them if they are not used by another application.</span></span>

> [!NOTE]
> <span data-ttu-id="e35fb-119">Windows インストーラーは、GAC にインストールされたアセンブリの参照カウントを保持します。</span><span class="sxs-lookup"><span data-stu-id="e35fb-119">Windows Installer maintains a reference count for assemblies installed in the GAC.</span></span> <span data-ttu-id="e35fb-120">アセンブリの参照カウントがゼロになる場合 (それが Windows インストーラー パッケージによってインストールされたアプリケーションによって使用されないことを示す) にのみ、アセンブリが GAC から削除されます。</span><span class="sxs-lookup"><span data-stu-id="e35fb-120">An assembly is removed from the GAC only when its reference count reaches zero, which indicates that it is not used by any application installed by a Windows Installer package.</span></span>

## <a name="see-also"></a><span data-ttu-id="e35fb-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="e35fb-121">See also</span></span>

- [<span data-ttu-id="e35fb-122">アセンブリとグローバル アセンブリ キャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="e35fb-122">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="e35fb-123">方法: アセンブリをグローバル アセンブリ キャッシュにインストールする</span><span class="sxs-lookup"><span data-stu-id="e35fb-123">How to: Install an Assembly into the Global Assembly Cache</span></span>](install-assembly-into-gac.md)
- [<span data-ttu-id="e35fb-124">Gacutil.exe (グローバル アセンブリ キャッシュ ツール)</span><span class="sxs-lookup"><span data-stu-id="e35fb-124">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
