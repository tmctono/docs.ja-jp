---
title: GetResolutionScope メソッド
ms.date: 03/30/2017
api_name:
- IALink.GetResolutionScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetResolutionScope
helpviewer_keywords:
- GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type:
- apiref
ms.openlocfilehash: f2b78b35db6306c82e389955c4824875bcf25334
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447226"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="696a0-102">GetResolutionScope メソッド</span><span class="sxs-lookup"><span data-stu-id="696a0-102">GetResolutionScope Method</span></span>
<span data-ttu-id="696a0-103">指定された型のスコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="696a0-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="696a0-104">構文</span><span class="sxs-lookup"><span data-stu-id="696a0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="696a0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="696a0-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="696a0-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="696a0-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="696a0-107">参照が必要なファイル。</span><span class="sxs-lookup"><span data-stu-id="696a0-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="696a0-108">型が定義されているファイルのトークン。通常は、 [Importfile メソッド](importfile-method.md)を使用して取得されます。</span><span class="sxs-lookup"><span data-stu-id="696a0-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="696a0-109">アセンブリまたはモジュール参照を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="696a0-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="696a0-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="696a0-110">Return Value</span></span>  
 <span data-ttu-id="696a0-111">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="696a0-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="696a0-112">要件</span><span class="sxs-lookup"><span data-stu-id="696a0-112">Requirements</span></span>  
 <span data-ttu-id="696a0-113">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="696a0-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="696a0-114">参照</span><span class="sxs-lookup"><span data-stu-id="696a0-114">See also</span></span>

- [<span data-ttu-id="696a0-115">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="696a0-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="696a0-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="696a0-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="696a0-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="696a0-117">ALink API</span></span>](index.md)
