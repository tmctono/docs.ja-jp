---
title: ISymUnmanagedVariable::GetStartOffset メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
ms.openlocfilehash: f2996349fd2bf1765a3de5b67d3296a25b1eaa5e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610367"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="95973-102">ISymUnmanagedVariable::GetStartOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="95973-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="95973-103">親内のこの変数の開始オフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="95973-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="95973-104">スコープ内のローカル変数の場合、開始オフセットはスコープに対して定義されたオフセット内になります。</span><span class="sxs-lookup"><span data-stu-id="95973-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95973-105">構文</span><span class="sxs-lookup"><span data-stu-id="95973-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95973-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="95973-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="95973-107">入出力開始オフセットを受け取るへのポインター `ULONG32` 。</span><span class="sxs-lookup"><span data-stu-id="95973-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95973-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="95973-108">Return Value</span></span>  
 <span data-ttu-id="95973-109">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="95973-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95973-110">要件</span><span class="sxs-lookup"><span data-stu-id="95973-110">Requirements</span></span>  
 <span data-ttu-id="95973-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="95973-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95973-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="95973-112">See also</span></span>

- [<span data-ttu-id="95973-113">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="95973-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="95973-114">GetEndOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="95973-114">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)
