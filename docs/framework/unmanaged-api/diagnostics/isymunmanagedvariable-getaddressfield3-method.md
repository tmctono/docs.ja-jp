---
title: ISymUnmanagedVariable::GetAddressField3 メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76199dd18799c9f51f37d5b92e589effd7f45a57
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778300"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="02579-102">ISymUnmanagedVariable::GetAddressField3 メソッド</span><span class="sxs-lookup"><span data-stu-id="02579-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="02579-103">この変数の 3 番目のアドレス フィールドを取得します。</span><span class="sxs-lookup"><span data-stu-id="02579-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="02579-104">その意味は、アドレスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="02579-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02579-105">構文</span><span class="sxs-lookup"><span data-stu-id="02579-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02579-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="02579-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="02579-107">[out]ポインターを`ULONG32`を受け取る 3 番目のアドレス フィールド。</span><span class="sxs-lookup"><span data-stu-id="02579-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02579-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="02579-108">Return Value</span></span>  
 <span data-ttu-id="02579-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="02579-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02579-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="02579-110">Requirements</span></span>  
 <span data-ttu-id="02579-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="02579-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02579-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="02579-112">See also</span></span>

- [<span data-ttu-id="02579-113">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02579-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="02579-114">GetAddressField1 メソッド</span><span class="sxs-lookup"><span data-stu-id="02579-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="02579-115">GetAddressField2 メソッド</span><span class="sxs-lookup"><span data-stu-id="02579-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="02579-116">GetAddressKind メソッド</span><span class="sxs-lookup"><span data-stu-id="02579-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
