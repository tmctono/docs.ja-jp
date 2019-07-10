---
title: ISymUnmanagedSourceServerModule::GetSourceServerData メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule.GetSourceServerData
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 22321dc8f8c4b8d9c2ae50b061a2ba105f92ebb7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746086"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="cfb61-102">ISymUnmanagedSourceServerModule::GetSourceServerData メソッド</span><span class="sxs-lookup"><span data-stu-id="cfb61-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="cfb61-103">モジュールのソース サーバーのデータを返します。</span><span class="sxs-lookup"><span data-stu-id="cfb61-103">Returns the source server data for the module.</span></span> <span data-ttu-id="cfb61-104">使用して、呼び出し元がリソースを解放する必要があります`CoTaskMemFree`します。</span><span class="sxs-lookup"><span data-stu-id="cfb61-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfb61-105">構文</span><span class="sxs-lookup"><span data-stu-id="cfb61-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfb61-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cfb61-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="cfb61-107">[out]ポインター、`ULONG32`ソース サーバーのデータのバイト単位のサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="cfb61-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="cfb61-108">[out]返されたポインター`pDataByteCount`値。</span><span class="sxs-lookup"><span data-stu-id="cfb61-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cfb61-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="cfb61-109">Return Value</span></span>  
 <span data-ttu-id="cfb61-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="cfb61-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfb61-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="cfb61-111">Requirements</span></span>  
 <span data-ttu-id="cfb61-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cfb61-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb61-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfb61-113">See also</span></span>

- [<span data-ttu-id="cfb61-114">ISymUnmanagedSourceServerModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cfb61-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
