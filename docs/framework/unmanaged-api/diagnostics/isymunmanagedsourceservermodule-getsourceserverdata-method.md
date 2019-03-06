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
ms.openlocfilehash: 69e83a5ff489881938c1e8410f765fd63f3b5d84
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479442"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="2a3ec-102">ISymUnmanagedSourceServerModule::GetSourceServerData メソッド</span><span class="sxs-lookup"><span data-stu-id="2a3ec-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="2a3ec-103">モジュールのソース サーバーのデータを返します。</span><span class="sxs-lookup"><span data-stu-id="2a3ec-103">Returns the source server data for the module.</span></span> <span data-ttu-id="2a3ec-104">使用して、呼び出し元がリソースを解放する必要があります`CoTaskMemFree`します。</span><span class="sxs-lookup"><span data-stu-id="2a3ec-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a3ec-105">構文</span><span class="sxs-lookup"><span data-stu-id="2a3ec-105">Syntax</span></span>  
  
```  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a3ec-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a3ec-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="2a3ec-107">[out]ポインター、`ULONG32`ソース サーバーのデータのバイト単位のサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="2a3ec-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="2a3ec-108">[out]返されたポインター`pDataByteCount`値。</span><span class="sxs-lookup"><span data-stu-id="2a3ec-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a3ec-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="2a3ec-109">Return Value</span></span>  
 <span data-ttu-id="2a3ec-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="2a3ec-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a3ec-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="2a3ec-111">Requirements</span></span>  
 <span data-ttu-id="2a3ec-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2a3ec-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3ec-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a3ec-113">See also</span></span>
- [<span data-ttu-id="2a3ec-114">ISymUnmanagedSourceServerModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a3ec-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
