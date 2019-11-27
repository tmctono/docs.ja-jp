---
title: ISymUnmanagedBinder3::GetReaderFromCallback メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
ms.openlocfilehash: a0cccc0adfc666cc8e373bc1f89c8f6f97068fde
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449303"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="ff784-102">ISymUnmanagedBinder3::GetReaderFromCallback メソッド</span><span class="sxs-lookup"><span data-stu-id="ff784-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="ff784-103">メモリからデバッグディレクトリ情報を取得するために、ユーザーが `IID_IDiaReadExeAtRVACallback` または `IID_IDiaReadExeAtOffsetCallback` のいずれかを使用して実装または提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ff784-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff784-104">構文</span><span class="sxs-lookup"><span data-stu-id="ff784-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff784-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ff784-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="ff784-106">からメタデータインポートインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ff784-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="ff784-107">からファイル名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ff784-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="ff784-108">から検索パスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ff784-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="ff784-109">からシンボルリーダーの検索を実行するときに使用するポリシーを指定する[Corsymsearchpolicyattributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)列挙体の値。</span><span class="sxs-lookup"><span data-stu-id="ff784-109">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="ff784-110">からコールバック関数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ff784-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="ff784-111">入出力返された[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)インターフェイスに設定されたポインター。</span><span class="sxs-lookup"><span data-stu-id="ff784-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff784-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="ff784-112">Return Value</span></span>  
 <span data-ttu-id="ff784-113">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ff784-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff784-114">要件</span><span class="sxs-lookup"><span data-stu-id="ff784-114">Requirements</span></span>  
 <span data-ttu-id="ff784-115">**ヘッダー:** CorSym .idl</span><span class="sxs-lookup"><span data-stu-id="ff784-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff784-116">参照</span><span class="sxs-lookup"><span data-stu-id="ff784-116">See also</span></span>

- [<span data-ttu-id="ff784-117">ISymUnmanagedBinder3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff784-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
