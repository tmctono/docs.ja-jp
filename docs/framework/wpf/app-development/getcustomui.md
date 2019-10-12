---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: e9ef32912c2afb3c99e46e1e14bb3daa5a2e99af
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005710"
---
# <a name="getcustomui"></a><span data-ttu-id="f260e-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="f260e-102">GetCustomUI</span></span>
<span data-ttu-id="f260e-103">実装されている場合、ホストからカスタムの進行状況とエラーメッセージを取得するために、プレゼンテーションの cluster.exe によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f260e-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f260e-104">構文</span><span class="sxs-lookup"><span data-stu-id="f260e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a><span data-ttu-id="f260e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f260e-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="f260e-106">入出力ホストから提供された進行状況のユーザーインターフェイスを格納しているアセンブリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f260e-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="f260e-107">入出力ホストから提供された進行状況のユーザーインターフェイスであるクラスの名前。可能であれば、<xref:System.Windows.Controls.Page> の XAML ファイルは最上位の要素です。</span><span class="sxs-lookup"><span data-stu-id="f260e-107">[out] The name of the class that is the host-supplied progress user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="f260e-108">このクラスは、`pwzProgressAssemblyName` によって指定されたアセンブリに存在します。</span><span class="sxs-lookup"><span data-stu-id="f260e-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="f260e-109">入出力ホストから提供されたエラーユーザーインターフェイスを格納しているアセンブリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f260e-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="f260e-110">入出力ホストから提供されたエラーユーザーインターフェイスであるクラスの名前。可能であれば、@no__t が0の XAML ファイルは最上位の要素です。</span><span class="sxs-lookup"><span data-stu-id="f260e-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="f260e-111">このクラスは、`pwzErrorAssemblyName` によって指定されたアセンブリに存在します。</span><span class="sxs-lookup"><span data-stu-id="f260e-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f260e-112">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="f260e-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="f260e-113">HRESULT:無視されます。</span><span class="sxs-lookup"><span data-stu-id="f260e-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f260e-114">コメント</span><span class="sxs-lookup"><span data-stu-id="f260e-114">Remarks</span></span>  
 <span data-ttu-id="f260e-115">ホストアプリケーションには、ホストの既定のユーザーインターフェイスが準拠していない可能性がある特定のテーマが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f260e-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="f260e-116">この場合、ホストアプリケーションは[GetCustomUI](getcustomui.md)を実装して、進行状況とエラーユーザーインターフェイスをプレゼンテーションの cluster.exe に返すことができます。</span><span class="sxs-lookup"><span data-stu-id="f260e-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="f260e-117">[GetCustomUI](getcustomui.md) は、既定のユーザーインターフェイスを使用する前に、常にを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f260e-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="f260e-118">この関数は、プレゼンテーションホストの初期化中に1回呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f260e-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f260e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f260e-119">See also</span></span>

- [<span data-ttu-id="f260e-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="f260e-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)
