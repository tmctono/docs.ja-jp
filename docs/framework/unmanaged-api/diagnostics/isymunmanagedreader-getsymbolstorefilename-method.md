---
title: ISymUnmanagedReader::GetSymbolStoreFileName メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymbolStoreFileName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 147b33a3f49f9163daea776779ca26f62561a84e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170379"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="d00cc-102">ISymUnmanagedReader::GetSymbolStoreFileName メソッド</span><span class="sxs-lookup"><span data-stu-id="d00cc-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="d00cc-103">シンボル ストアのディスク上のファイル名を提供します。</span><span class="sxs-lookup"><span data-stu-id="d00cc-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d00cc-104">構文</span><span class="sxs-lookup"><span data-stu-id="d00cc-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d00cc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d00cc-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="d00cc-106">[in]サイズ、`szName`バッファー。</span><span class="sxs-lookup"><span data-stu-id="d00cc-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d00cc-107">[out]返される名前の長さを受け取る変数へのポインター`szName`終端の null を含むです。</span><span class="sxs-lookup"><span data-stu-id="d00cc-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="d00cc-108">[out]シンボル ストアのファイル名を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d00cc-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d00cc-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="d00cc-109">Return Value</span></span>  
 <span data-ttu-id="d00cc-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="d00cc-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d00cc-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d00cc-111">Requirements</span></span>  
 <span data-ttu-id="d00cc-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d00cc-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d00cc-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d00cc-113">See also</span></span>

- [<span data-ttu-id="d00cc-114">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d00cc-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
