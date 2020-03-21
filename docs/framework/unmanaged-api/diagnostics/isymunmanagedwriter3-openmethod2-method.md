---
title: ISymUnmanagedWriter3::OpenMethod2 メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.OpenMethod2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type:
- apiref
ms.openlocfilehash: 0c112819ef3bc4f9a7146ee80f55202ff89d689a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178314"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="5ec86-102">ISymUnmanagedWriter3::OpenMethod2 メソッド</span><span class="sxs-lookup"><span data-stu-id="5ec86-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="5ec86-103">メソッドを開き、イメージ内の実際のセクション オフセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="5ec86-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ec86-104">構文</span><span class="sxs-lookup"><span data-stu-id="5ec86-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ec86-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5ec86-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="5ec86-106">[in]開くメソッドのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="5ec86-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="5ec86-107">[in]イメージ内のセクション オフセット。</span><span class="sxs-lookup"><span data-stu-id="5ec86-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="5ec86-108">[in]イメージ内のオフセット。</span><span class="sxs-lookup"><span data-stu-id="5ec86-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ec86-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="5ec86-109">Return Value</span></span>  
 <span data-ttu-id="5ec86-110">メソッドが成功した場合はS_OK。それ以外の場合は、E_FAILまたはその他のエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="5ec86-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ec86-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="5ec86-111">Requirements</span></span>  
 <span data-ttu-id="5ec86-112">**ヘッダー:** コーシム.idl,コーシム.h</span><span class="sxs-lookup"><span data-stu-id="5ec86-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ec86-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ec86-113">See also</span></span>

- [<span data-ttu-id="5ec86-114">ISymUnmanagedWriter3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ec86-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="5ec86-115">OpenMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="5ec86-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
