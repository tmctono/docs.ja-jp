---
title: ISymUnmanagedReader::GetNamespaces メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 570532433483e9d0a08f4d685087c0736e135390
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076732"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="d1e07-102">ISymUnmanagedReader::GetNamespaces メソッド</span><span class="sxs-lookup"><span data-stu-id="d1e07-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="d1e07-103">このシンボル ストア内のグローバル スコープで定義された名前空間を取得します。</span><span class="sxs-lookup"><span data-stu-id="d1e07-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1e07-104">構文</span><span class="sxs-lookup"><span data-stu-id="d1e07-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1e07-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d1e07-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="d1e07-106">[in]名前空間の配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="d1e07-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="d1e07-107">[out]名前空間の一覧の長さを受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d1e07-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="d1e07-108">[out]名前空間の一覧を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d1e07-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1e07-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="d1e07-109">Return Value</span></span>  
 <span data-ttu-id="d1e07-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="d1e07-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1e07-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d1e07-111">Requirements</span></span>  
 <span data-ttu-id="d1e07-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d1e07-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e07-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1e07-113">See also</span></span>

- [<span data-ttu-id="d1e07-114">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d1e07-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
