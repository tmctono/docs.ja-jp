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
ms.openlocfilehash: b3674c4058dba2f6185418b55b35eefb14c312f6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431243"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="ecd7f-102">ISymUnmanagedReader::GetSymbolStoreFileName メソッド</span><span class="sxs-lookup"><span data-stu-id="ecd7f-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="ecd7f-103">シンボルストアのディスク上のファイル名を提供します。</span><span class="sxs-lookup"><span data-stu-id="ecd7f-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecd7f-104">構文</span><span class="sxs-lookup"><span data-stu-id="ecd7f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecd7f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ecd7f-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="ecd7f-106">から`szName` バッファーのサイズ。</span><span class="sxs-lookup"><span data-stu-id="ecd7f-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ecd7f-107">入出力Null 終了を含む `szName`で返された名前の長さを受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ecd7f-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="ecd7f-108">入出力シンボルストアのファイル名を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ecd7f-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ecd7f-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="ecd7f-109">Return Value</span></span>  
 <span data-ttu-id="ecd7f-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ecd7f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecd7f-111">要件</span><span class="sxs-lookup"><span data-stu-id="ecd7f-111">Requirements</span></span>  
 <span data-ttu-id="ecd7f-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="ecd7f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecd7f-113">参照</span><span class="sxs-lookup"><span data-stu-id="ecd7f-113">See also</span></span>

- [<span data-ttu-id="ecd7f-114">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ecd7f-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
