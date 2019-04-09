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
ms.openlocfilehash: 66f8804c911e053758442670afb3c3f27d0f7453
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130053"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="2df31-102">ISymUnmanagedWriter::CloseNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="2df31-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="2df31-103">終了は、最近名前空間を開きます。</span><span class="sxs-lookup"><span data-stu-id="2df31-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2df31-104">構文</span><span class="sxs-lookup"><span data-stu-id="2df31-104">Syntax</span></span>  
  
```  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2df31-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="2df31-105">Return Value</span></span>  
 <span data-ttu-id="2df31-106">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="2df31-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2df31-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="2df31-107">Requirements</span></span>  
 <span data-ttu-id="2df31-108">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2df31-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df31-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="2df31-109">See also</span></span>

- [<span data-ttu-id="2df31-110">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2df31-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="2df31-111">OpenNamespace メソッド</span><span class="sxs-lookup"><span data-stu-id="2df31-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)
