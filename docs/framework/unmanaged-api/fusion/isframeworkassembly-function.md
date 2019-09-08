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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 269e3702c21532f377735ba6087abb1603dde4f7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796318"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="78a54-102">IsFrameworkAssembly 関数</span><span class="sxs-lookup"><span data-stu-id="78a54-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="78a54-103">指定したアセンブリが管理されているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="78a54-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a54-104">構文</span><span class="sxs-lookup"><span data-stu-id="78a54-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="78a54-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="78a54-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="78a54-106">から確認するアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="78a54-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="78a54-107">入出力アセンブリが管理されているかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="78a54-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="78a54-108">からアセンブリの一意の id を含む、正規化されていない文字列。</span><span class="sxs-lookup"><span data-stu-id="78a54-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="78a54-109">[入力] `pwzFrameworkAssemblyIdentity` のサイズ。</span><span class="sxs-lookup"><span data-stu-id="78a54-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78a54-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="78a54-110">Remarks</span></span>  
 <span data-ttu-id="78a54-111">`pwzAssemblyReference`パラメーターは、アセンブリの名前を含む文字列へのポインターです。</span><span class="sxs-lookup"><span data-stu-id="78a54-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="78a54-112">このアセンブリが .NET Framework の一部である場合、 `pbIsFrameworkAssembly`パラメーターにはの`true`ブール値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="78a54-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="78a54-113">名前付きアセンブリが .NET Framework に含まれていない場合、また`pwzAssemblyReference`はパラメーターがアセンブリの名前を`pbIsFrameworkAssembly`指定しない場合、に`false`はブール値のが格納されます。</span><span class="sxs-lookup"><span data-stu-id="78a54-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78a54-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="78a54-114">Requirements</span></span>  
 <span data-ttu-id="78a54-115">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="78a54-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a54-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="78a54-116">See also</span></span>

- [<span data-ttu-id="78a54-117">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="78a54-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
