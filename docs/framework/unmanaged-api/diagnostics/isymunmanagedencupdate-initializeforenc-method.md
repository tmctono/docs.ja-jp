---
title: ISymUnmanagedENCUpdate::InitializeForEnc メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.InitializeForEnc
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc
helpviewer_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc method [.NET Framework debugging]
- InitializeForEnc method [.NET Framework debugging]
ms.assetid: 796b2154-b53c-4d07-9e67-80fd6064725a
topic_type:
- apiref
ms.openlocfilehash: f612e38398f8c1320ba87722498400d70ec8bff0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614540"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a><span data-ttu-id="df937-102">ISymUnmanagedENCUpdate::InitializeForEnc メソッド</span><span class="sxs-lookup"><span data-stu-id="df937-102">ISymUnmanagedENCUpdate::InitializeForEnc Method</span></span>
<span data-ttu-id="df937-103">[ISymUnmanagedENCUpdate:: UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md)メソッドの最初の呼び出しの前にメソッドの境界を計算できるようにします。</span><span class="sxs-lookup"><span data-stu-id="df937-103">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df937-104">構文</span><span class="sxs-lookup"><span data-stu-id="df937-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a><span data-ttu-id="df937-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="df937-105">Return Value</span></span>  
 <span data-ttu-id="df937-106">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="df937-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df937-107">要件</span><span class="sxs-lookup"><span data-stu-id="df937-107">Requirements</span></span>  
 <span data-ttu-id="df937-108">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="df937-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df937-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="df937-109">See also</span></span>

- [<span data-ttu-id="df937-110">ISymUnmanagedENCUpdate インターフェイス</span><span class="sxs-lookup"><span data-stu-id="df937-110">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
