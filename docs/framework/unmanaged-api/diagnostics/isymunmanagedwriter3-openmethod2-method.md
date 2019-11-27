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
ms.openlocfilehash: 3a628aec0823c5db07d31d33813a020606906163
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438130"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="d8ad8-102">ISymUnmanagedWriter3::OpenMethod2 メソッド</span><span class="sxs-lookup"><span data-stu-id="d8ad8-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="d8ad8-103">メソッドを開き、イメージ内の実際のセクションオフセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="d8ad8-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8ad8-104">構文</span><span class="sxs-lookup"><span data-stu-id="d8ad8-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8ad8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d8ad8-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="d8ad8-106">から開くメソッドのメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="d8ad8-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="d8ad8-107">からイメージ内のセクションオフセット。</span><span class="sxs-lookup"><span data-stu-id="d8ad8-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="d8ad8-108">からイメージ内のオフセット。</span><span class="sxs-lookup"><span data-stu-id="d8ad8-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8ad8-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="d8ad8-109">Return Value</span></span>  
 <span data-ttu-id="d8ad8-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8ad8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8ad8-111">要件</span><span class="sxs-lookup"><span data-stu-id="d8ad8-111">Requirements</span></span>  
 <span data-ttu-id="d8ad8-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="d8ad8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8ad8-113">参照</span><span class="sxs-lookup"><span data-stu-id="d8ad8-113">See also</span></span>

- [<span data-ttu-id="d8ad8-114">ISymUnmanagedWriter3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d8ad8-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="d8ad8-115">OpenMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="d8ad8-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
