---
title: ISymUnmanagedScope::GetMethod メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type:
- apiref
ms.openlocfilehash: cdbffe71540b51ff539a45861546efd761761892
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615372"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="26e88-102">ISymUnmanagedScope::GetMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="26e88-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="26e88-103">このスコープを格納しているメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="26e88-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26e88-104">構文</span><span class="sxs-lookup"><span data-stu-id="26e88-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26e88-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26e88-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="26e88-106">入出力返された[ISymUnmanagedMethod](isymunmanagedmethod-interface.md)インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="26e88-106">[out] A pointer to the returned [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26e88-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="26e88-107">Return Value</span></span>  
 <span data-ttu-id="26e88-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="26e88-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26e88-109">要件</span><span class="sxs-lookup"><span data-stu-id="26e88-109">Requirements</span></span>  
 <span data-ttu-id="26e88-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="26e88-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e88-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="26e88-111">See also</span></span>

- [<span data-ttu-id="26e88-112">ISymUnmanagedScope インターフェイス</span><span class="sxs-lookup"><span data-stu-id="26e88-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
