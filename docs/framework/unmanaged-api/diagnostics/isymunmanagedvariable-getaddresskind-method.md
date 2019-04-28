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
ms.openlocfilehash: eae5b21af3bcdca911ec13067a61bb957d4ae6ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797580"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="791bd-102">ISymUnmanagedVariable::GetAddressKind メソッド</span><span class="sxs-lookup"><span data-stu-id="791bd-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="791bd-103">この変数のアドレスの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="791bd-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="791bd-104">構文</span><span class="sxs-lookup"><span data-stu-id="791bd-104">Syntax</span></span>  
  
```  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="791bd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="791bd-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="791bd-106">[out]ポインターを`ULONG32`値を受け取る。</span><span class="sxs-lookup"><span data-stu-id="791bd-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="791bd-107">使用可能な値が定義されている、 [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="791bd-107">The possible values are defined in the [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="791bd-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="791bd-108">Return Value</span></span>  
 <span data-ttu-id="791bd-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="791bd-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="791bd-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="791bd-110">Requirements</span></span>  
 <span data-ttu-id="791bd-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="791bd-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="791bd-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="791bd-112">See also</span></span>

- [<span data-ttu-id="791bd-113">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="791bd-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
