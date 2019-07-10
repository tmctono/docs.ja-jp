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
ms.openlocfilehash: 2e686e332cf1d35537e5d4306a3a9cbf9d46c47e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752371"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="7d692-102">ISymUnmanagedWriter3::OpenMethod2 メソッド</span><span class="sxs-lookup"><span data-stu-id="7d692-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="7d692-103">メソッドが開き、イメージで実際のセクションのオフセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="7d692-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d692-104">構文</span><span class="sxs-lookup"><span data-stu-id="7d692-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d692-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d692-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="7d692-106">[in]開かれているメソッドのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="7d692-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="7d692-107">[in]イメージ内のセクションのオフセット。</span><span class="sxs-lookup"><span data-stu-id="7d692-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="7d692-108">[in]イメージ内のオフセット。</span><span class="sxs-lookup"><span data-stu-id="7d692-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d692-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="7d692-109">Return Value</span></span>  
 <span data-ttu-id="7d692-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="7d692-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d692-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="7d692-111">Requirements</span></span>  
 <span data-ttu-id="7d692-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7d692-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d692-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d692-113">See also</span></span>

- [<span data-ttu-id="7d692-114">ISymUnmanagedWriter3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7d692-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="7d692-115">OpenMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="7d692-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
