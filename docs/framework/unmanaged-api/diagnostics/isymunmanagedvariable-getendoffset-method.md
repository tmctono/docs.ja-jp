---
title: ISymUnmanagedVariable::GetEndOffset メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
ms.openlocfilehash: 91117eae23d38f3bc608f3203ebe53f92516c9c9
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610497"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="8982a-102">ISymUnmanagedVariable::GetEndOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="8982a-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="8982a-103">親内のこの変数の終了オフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="8982a-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="8982a-104">スコープ内のローカル変数の場合は、スコープに対して定義されたオフセット内に終了オフセットが適用されます。</span><span class="sxs-lookup"><span data-stu-id="8982a-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8982a-105">構文</span><span class="sxs-lookup"><span data-stu-id="8982a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8982a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8982a-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="8982a-107">入出力終了オフセットを受け取るへのポインター `ULONG32` 。</span><span class="sxs-lookup"><span data-stu-id="8982a-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8982a-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="8982a-108">Return Value</span></span>  
 <span data-ttu-id="8982a-109">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="8982a-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8982a-110">要件</span><span class="sxs-lookup"><span data-stu-id="8982a-110">Requirements</span></span>  
 <span data-ttu-id="8982a-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="8982a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8982a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8982a-112">See also</span></span>

- [<span data-ttu-id="8982a-113">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8982a-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="8982a-114">GetStartOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="8982a-114">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)
