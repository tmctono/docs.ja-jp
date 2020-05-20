---
title: ISymUnmanagedConstant::GetValue メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
ms.openlocfilehash: 8e20d2e0f3d5cb6dc7444c8e78665b6c8b82d2de
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441475"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="53692-102">ISymUnmanagedConstant::GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="53692-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="53692-103">定数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="53692-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53692-104">構文</span><span class="sxs-lookup"><span data-stu-id="53692-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53692-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="53692-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="53692-106">入出力値を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="53692-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53692-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="53692-107">Return Value</span></span>  
 <span data-ttu-id="53692-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="53692-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53692-109">要件</span><span class="sxs-lookup"><span data-stu-id="53692-109">Requirements</span></span>  
 <span data-ttu-id="53692-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="53692-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53692-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="53692-111">See also</span></span>

- [<span data-ttu-id="53692-112">ISymUnmanagedConstant インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53692-112">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="53692-113">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="53692-113">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="53692-114">GetSignature メソッド</span><span class="sxs-lookup"><span data-stu-id="53692-114">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
