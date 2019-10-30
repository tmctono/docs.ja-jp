---
title: IsFrameworkAssembly 関数
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
ms.openlocfilehash: e30b6f2d2254d2d107c4c82a2c5664850ce6ec23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123068"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="c57d9-102">IsFrameworkAssembly 関数</span><span class="sxs-lookup"><span data-stu-id="c57d9-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="c57d9-103">指定したアセンブリが管理されているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="c57d9-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c57d9-104">構文</span><span class="sxs-lookup"><span data-stu-id="c57d9-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="c57d9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c57d9-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="c57d9-106">から確認するアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="c57d9-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="c57d9-107">入出力アセンブリが管理されているかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="c57d9-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="c57d9-108">からアセンブリの一意の id を含む、正規化されていない文字列。</span><span class="sxs-lookup"><span data-stu-id="c57d9-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="c57d9-109">[入力] `pwzFrameworkAssemblyIdentity` のサイズ。</span><span class="sxs-lookup"><span data-stu-id="c57d9-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c57d9-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="c57d9-110">Remarks</span></span>  
 <span data-ttu-id="c57d9-111">`pwzAssemblyReference` パラメーターは、アセンブリの名前を含む文字列へのポインターです。</span><span class="sxs-lookup"><span data-stu-id="c57d9-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="c57d9-112">このアセンブリが .NET Framework の一部である場合、`pbIsFrameworkAssembly` パラメーターには `true`のブール値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c57d9-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="c57d9-113">名前付きアセンブリが .NET Framework の一部でない場合、または `pwzAssemblyReference` パラメーターがアセンブリの名前を指定しない場合、`pbIsFrameworkAssembly` には `false`のブール値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c57d9-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c57d9-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="c57d9-114">Requirements</span></span>  
 <span data-ttu-id="c57d9-115">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c57d9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c57d9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c57d9-116">See also</span></span>

- [<span data-ttu-id="c57d9-117">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="c57d9-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
