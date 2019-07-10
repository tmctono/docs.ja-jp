---
title: ISymUnmanagedWriter::CloseNamespace メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ed618847d398bb4dcccb8ecebabdc947390c874
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778173"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="a010f-102">ISymUnmanagedWriter::CloseNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="a010f-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="a010f-103">終了は、最近名前空間を開きます。</span><span class="sxs-lookup"><span data-stu-id="a010f-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a010f-104">構文</span><span class="sxs-lookup"><span data-stu-id="a010f-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a010f-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="a010f-105">Return Value</span></span>  
 <span data-ttu-id="a010f-106">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="a010f-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a010f-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="a010f-107">Requirements</span></span>  
 <span data-ttu-id="a010f-108">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a010f-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a010f-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="a010f-109">See also</span></span>

- [<span data-ttu-id="a010f-110">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a010f-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="a010f-111">OpenNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="a010f-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)
