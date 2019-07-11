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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9b6ca8482de1eaf021d65f63a349f37cff15f8ce
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774698"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a><span data-ttu-id="1b615-102">ISymUnmanagedENCUpdate::InitializeForEnc メソッド</span><span class="sxs-lookup"><span data-stu-id="1b615-102">ISymUnmanagedENCUpdate::InitializeForEnc Method</span></span>
<span data-ttu-id="1b615-103">により、最初の呼び出しの前に計算するメソッドの境界、 [isymunmanagedencupdate::updatesymbolstore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="1b615-103">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b615-104">構文</span><span class="sxs-lookup"><span data-stu-id="1b615-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1b615-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="1b615-105">Return Value</span></span>  
 <span data-ttu-id="1b615-106">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="1b615-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b615-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="1b615-107">Requirements</span></span>  
 <span data-ttu-id="1b615-108">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1b615-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b615-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b615-109">See also</span></span>

- [<span data-ttu-id="1b615-110">ISymUnmanagedENCUpdate インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b615-110">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
