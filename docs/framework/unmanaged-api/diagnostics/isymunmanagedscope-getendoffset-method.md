---
title: ISymUnmanagedScope::GetEndOffset メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b99825a210a7a0f1253a01485a61bdbfeacf160
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751289"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="7eb93-102">ISymUnmanagedScope::GetEndOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="7eb93-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="7eb93-103">このスコープの終了オフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="7eb93-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eb93-104">構文</span><span class="sxs-lookup"><span data-stu-id="7eb93-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7eb93-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7eb93-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="7eb93-106">[out]ポインターを`ULONG32`を受け取る、終了オフセット。</span><span class="sxs-lookup"><span data-stu-id="7eb93-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7eb93-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="7eb93-107">Return Value</span></span>  
 <span data-ttu-id="7eb93-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="7eb93-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eb93-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="7eb93-109">Requirements</span></span>  
 <span data-ttu-id="7eb93-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7eb93-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eb93-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="7eb93-111">See also</span></span>

- [<span data-ttu-id="7eb93-112">ISymUnmanagedScope インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7eb93-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="7eb93-113">GetStartOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="7eb93-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
