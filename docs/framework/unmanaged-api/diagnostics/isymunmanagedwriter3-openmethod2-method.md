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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3dcb1327ad50761a8268e8adc7b1e976cae0b3a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200299"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="292ab-102">ISymUnmanagedWriter3::OpenMethod2 メソッド</span><span class="sxs-lookup"><span data-stu-id="292ab-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="292ab-103">メソッドが開き、イメージで実際のセクションのオフセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="292ab-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="292ab-104">構文</span><span class="sxs-lookup"><span data-stu-id="292ab-104">Syntax</span></span>  
  
```  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="292ab-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="292ab-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="292ab-106">[in]開かれているメソッドのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="292ab-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="292ab-107">[in]イメージ内のセクションのオフセット。</span><span class="sxs-lookup"><span data-stu-id="292ab-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="292ab-108">[in]イメージ内のオフセット。</span><span class="sxs-lookup"><span data-stu-id="292ab-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="292ab-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="292ab-109">Return Value</span></span>  
 <span data-ttu-id="292ab-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="292ab-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="292ab-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="292ab-111">Requirements</span></span>  
 <span data-ttu-id="292ab-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="292ab-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="292ab-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="292ab-113">See also</span></span>

- [<span data-ttu-id="292ab-114">ISymUnmanagedWriter3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="292ab-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="292ab-115">OpenMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="292ab-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
