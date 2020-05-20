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
ms.openlocfilehash: 093c5e3e64395c8946acd9201990d132e8111fc7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610588"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="aabfb-102">ISymUnmanagedVariable::GetAddressKind メソッド</span><span class="sxs-lookup"><span data-stu-id="aabfb-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="aabfb-103">この変数のアドレスの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="aabfb-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aabfb-104">構文</span><span class="sxs-lookup"><span data-stu-id="aabfb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aabfb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aabfb-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="aabfb-106">入出力値を受け取るへのポインター `ULONG32` 。</span><span class="sxs-lookup"><span data-stu-id="aabfb-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="aabfb-107">使用可能な値は、 [Corsymaddrkind](corsymaddrkind-enumeration.md)列挙体で定義されています。</span><span class="sxs-lookup"><span data-stu-id="aabfb-107">The possible values are defined in the [CorSymAddrKind](corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aabfb-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="aabfb-108">Return Value</span></span>  
 <span data-ttu-id="aabfb-109">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="aabfb-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aabfb-110">要件</span><span class="sxs-lookup"><span data-stu-id="aabfb-110">Requirements</span></span>  
 <span data-ttu-id="aabfb-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="aabfb-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aabfb-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="aabfb-112">See also</span></span>

- [<span data-ttu-id="aabfb-113">ISymUnmanagedVariable インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aabfb-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
