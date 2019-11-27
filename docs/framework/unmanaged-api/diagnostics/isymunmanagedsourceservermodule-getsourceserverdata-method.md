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
ms.openlocfilehash: f25150d037a2f6fabb700f2c4bf2191e8e402a8e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446210"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="4bd61-102">ISymUnmanagedSourceServerModule::GetSourceServerData メソッド</span><span class="sxs-lookup"><span data-stu-id="4bd61-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="4bd61-103">モジュールのソースサーバーデータを返します。</span><span class="sxs-lookup"><span data-stu-id="4bd61-103">Returns the source server data for the module.</span></span> <span data-ttu-id="4bd61-104">呼び出し元は、`CoTaskMemFree`を使用してリソースを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bd61-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bd61-105">構文</span><span class="sxs-lookup"><span data-stu-id="4bd61-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bd61-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4bd61-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="4bd61-107">入出力転送元サーバーのデータのサイズ (バイト単位) を受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4bd61-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="4bd61-108">入出力返された `pDataByteCount` 値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4bd61-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4bd61-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="4bd61-109">Return Value</span></span>  
 <span data-ttu-id="4bd61-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="4bd61-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bd61-111">要件</span><span class="sxs-lookup"><span data-stu-id="4bd61-111">Requirements</span></span>  
 <span data-ttu-id="4bd61-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="4bd61-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bd61-113">参照</span><span class="sxs-lookup"><span data-stu-id="4bd61-113">See also</span></span>

- [<span data-ttu-id="4bd61-114">ISymUnmanagedSourceServerModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4bd61-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
