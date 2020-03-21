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
ms.openlocfilehash: 6904271ed90cf733b9221178927bc680d76b58a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176579"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="969eb-102">ISymUnmanagedSourceServerModule::GetSourceServerData メソッド</span><span class="sxs-lookup"><span data-stu-id="969eb-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="969eb-103">モジュールのソース サーバー データを返します。</span><span class="sxs-lookup"><span data-stu-id="969eb-103">Returns the source server data for the module.</span></span> <span data-ttu-id="969eb-104">呼び出し元は、`CoTaskMemFree`を使用してリソースを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="969eb-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="969eb-105">構文</span><span class="sxs-lookup"><span data-stu-id="969eb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="969eb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="969eb-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="969eb-107">[アウト]ソース サーバー`ULONG32`データのサイズ (バイト単位) を受け取るを指すポインター。</span><span class="sxs-lookup"><span data-stu-id="969eb-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="969eb-108">[アウト]戻り`pDataByteCount`値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="969eb-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="969eb-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="969eb-109">Return Value</span></span>  
 <span data-ttu-id="969eb-110">メソッドが成功した場合はS_OK。それ以外の場合は、E_FAILまたはその他のエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="969eb-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="969eb-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="969eb-111">Requirements</span></span>  
 <span data-ttu-id="969eb-112">**ヘッダー:** コーシム.idl,コーシム.h</span><span class="sxs-lookup"><span data-stu-id="969eb-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="969eb-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="969eb-113">See also</span></span>

- [<span data-ttu-id="969eb-114">ISymUnmanagedSourceServerModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="969eb-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
