---
title: ISymUnmanagedScope::GetLocalCount メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
ms.openlocfilehash: 9ffba23e3821c48c9b0708e4b6b617db4ddc5959
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83611264"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="a00fc-102">ISymUnmanagedScope::GetLocalCount メソッド</span><span class="sxs-lookup"><span data-stu-id="a00fc-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="a00fc-103">このスコープ内で定義されているローカル変数の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="a00fc-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a00fc-104">構文</span><span class="sxs-lookup"><span data-stu-id="a00fc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a00fc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a00fc-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a00fc-106">入出力`ULONG32`ローカル変数の数を受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a00fc-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a00fc-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="a00fc-107">Return Value</span></span>  
 <span data-ttu-id="a00fc-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a00fc-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a00fc-109">要件</span><span class="sxs-lookup"><span data-stu-id="a00fc-109">Requirements</span></span>  
 <span data-ttu-id="a00fc-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="a00fc-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a00fc-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="a00fc-111">See also</span></span>

- [<span data-ttu-id="a00fc-112">ISymUnmanagedScope インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a00fc-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
