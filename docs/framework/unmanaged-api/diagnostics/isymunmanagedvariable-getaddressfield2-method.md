---
title: ISymUnmanagedVariable::GetAddressField2 メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField2
helpviewer_keywords:
- GetAddressField2 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField2 method [.NET Framework debugging]
ms.assetid: 1f25b294-72b6-4882-a49b-6c9d364b6008
topic_type:
- apiref
ms.openlocfilehash: 6256d052780b1c610e61267be2517954d722a42d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610601"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="9afce-102">ISymUnmanagedVariable::GetAddressField2 メソッド</span><span class="sxs-lookup"><span data-stu-id="9afce-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>
<span data-ttu-id="9afce-103">この変数の2番目のアドレスフィールドを取得します。</span><span class="sxs-lookup"><span data-stu-id="9afce-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="9afce-104">その意味は、アドレスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="9afce-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9afce-105">構文</span><span class="sxs-lookup"><span data-stu-id="9afce-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9afce-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9afce-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="9afce-107">入出力`ULONG32`2 番目のアドレスフィールドを受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9afce-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9afce-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="9afce-108">Return Value</span></span>  
 <span data-ttu-id="9afce-109">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="9afce-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9afce-110">要件</span><span class="sxs-lookup"><span data-stu-id="9afce-110">Requirements</span></span>  
 <span data-ttu-id="9afce-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="9afce-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9afce-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9afce-112">See also</span></span>

- [<span data-ttu-id="9afce-113">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9afce-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="9afce-114">GetAddressField1 メソッド</span><span class="sxs-lookup"><span data-stu-id="9afce-114">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="9afce-115">GetAddressField3 メソッド</span><span class="sxs-lookup"><span data-stu-id="9afce-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="9afce-116">GetAddressKind メソッド</span><span class="sxs-lookup"><span data-stu-id="9afce-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
