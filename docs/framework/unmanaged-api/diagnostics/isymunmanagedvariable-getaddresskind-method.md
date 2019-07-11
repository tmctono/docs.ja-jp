---
title: ISymUnmanagedVariable::GetAddressKind メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressKind
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressKind
helpviewer_keywords:
- GetAddressKind method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressKind method [.NET Framework debugging]
ms.assetid: a71563c0-62f2-4eb4-970c-825d61827613
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b5fd3c5e5a7a706929af849ec3a66dd6c41b3bd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778284"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="2e17c-102">ISymUnmanagedVariable::GetAddressKind メソッド</span><span class="sxs-lookup"><span data-stu-id="2e17c-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="2e17c-103">この変数のアドレスの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="2e17c-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e17c-104">構文</span><span class="sxs-lookup"><span data-stu-id="2e17c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e17c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e17c-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="2e17c-106">[out]ポインターを`ULONG32`値を受け取る。</span><span class="sxs-lookup"><span data-stu-id="2e17c-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="2e17c-107">使用可能な値が定義されている、 [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="2e17c-107">The possible values are defined in the [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e17c-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="2e17c-108">Return Value</span></span>  
 <span data-ttu-id="2e17c-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="2e17c-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e17c-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="2e17c-110">Requirements</span></span>  
 <span data-ttu-id="2e17c-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2e17c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e17c-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e17c-112">See also</span></span>

- [<span data-ttu-id="2e17c-113">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2e17c-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
