---
title: ISymUnmanagedVariable::GetAddressField1 メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField1
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type:
- apiref
ms.openlocfilehash: a59b50009e7f0ab2fff1b8439e368234403822c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446137"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="f5f55-102">ISymUnmanagedVariable::GetAddressField1 メソッド</span><span class="sxs-lookup"><span data-stu-id="f5f55-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="f5f55-103">この変数の最初のアドレスフィールドを取得します。</span><span class="sxs-lookup"><span data-stu-id="f5f55-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="f5f55-104">その意味は、アドレスの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f5f55-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5f55-105">構文</span><span class="sxs-lookup"><span data-stu-id="f5f55-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5f55-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5f55-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f5f55-107">入出力最初のアドレスフィールドを受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f5f55-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5f55-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="f5f55-108">Return Value</span></span>  
 <span data-ttu-id="f5f55-109">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5f55-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5f55-110">要件</span><span class="sxs-lookup"><span data-stu-id="f5f55-110">Requirements</span></span>  
 <span data-ttu-id="f5f55-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="f5f55-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5f55-112">参照</span><span class="sxs-lookup"><span data-stu-id="f5f55-112">See also</span></span>

- [<span data-ttu-id="f5f55-113">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f5f55-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="f5f55-114">GetAddressField2 メソッド</span><span class="sxs-lookup"><span data-stu-id="f5f55-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="f5f55-115">GetAddressField3 メソッド</span><span class="sxs-lookup"><span data-stu-id="f5f55-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="f5f55-116">GetAddressKind メソッド</span><span class="sxs-lookup"><span data-stu-id="f5f55-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
