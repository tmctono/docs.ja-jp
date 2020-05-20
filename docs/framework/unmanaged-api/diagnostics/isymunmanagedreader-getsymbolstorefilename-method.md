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
ms.openlocfilehash: 6ffab3b2f81680404f870cfd63ae5125173a346c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615515"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="2ce24-102">ISymUnmanagedReader::GetSymbolStoreFileName メソッド</span><span class="sxs-lookup"><span data-stu-id="2ce24-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="2ce24-103">シンボルストアのディスク上のファイル名を提供します。</span><span class="sxs-lookup"><span data-stu-id="2ce24-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ce24-104">構文</span><span class="sxs-lookup"><span data-stu-id="2ce24-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ce24-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ce24-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="2ce24-106">からバッファーのサイズ `szName` 。</span><span class="sxs-lookup"><span data-stu-id="2ce24-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2ce24-107">入出力Null 終了を含む、で返された名前の長さを受け取る変数へのポインター `szName` 。</span><span class="sxs-lookup"><span data-stu-id="2ce24-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="2ce24-108">入出力シンボルストアのファイル名を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2ce24-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ce24-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="2ce24-109">Return Value</span></span>  
 <span data-ttu-id="2ce24-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ce24-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ce24-111">要件</span><span class="sxs-lookup"><span data-stu-id="2ce24-111">Requirements</span></span>  
 <span data-ttu-id="2ce24-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="2ce24-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ce24-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ce24-113">See also</span></span>

- [<span data-ttu-id="2ce24-114">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ce24-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
