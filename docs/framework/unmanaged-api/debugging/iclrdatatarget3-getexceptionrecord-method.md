---
title: ICLRDataTarget3::GetExceptionRecord メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6643c2af-2ee6-4789-aa25-1d8eaf500c94
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca53995daec372c75aa8c0beb305a6c36f1e6e07
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489776"
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a><span data-ttu-id="c2742-102">ICLRDataTarget3::GetExceptionRecord メソッド</span><span class="sxs-lookup"><span data-stu-id="c2742-102">ICLRDataTarget3::GetExceptionRecord Method</span></span>
<span data-ttu-id="c2742-103">ターゲット プロセスに関連付けられた例外レコードを取得するために、共通言語ランタイム (CLR: Common Language Runtime) データ アクセス サービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c2742-103">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span> <span data-ttu-id="c2742-104">たとえば、ダンプ ターゲットについて、これと等価になります経由で渡された例外レコード、`ExceptionParam`への引数、 [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) Windows デバッグ ヘルプ ライブラリ (DbgHelp) の関数。</span><span class="sxs-lookup"><span data-stu-id="c2742-104">For example, for a dump target, this would be equivalent to the exception record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2742-105">構文</span><span class="sxs-lookup"><span data-stu-id="c2742-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2742-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c2742-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="c2742-107">[入力] 入力バッファー サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="c2742-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="c2742-108">これと同じである必要があります`sizeof(` [MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception)`)`します。</span><span class="sxs-lookup"><span data-stu-id="c2742-108">This must be equal to `sizeof(`[MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception)`)`.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="c2742-109">[出力] 実際にバッファーに書き込まれるバイト数を受け取る `ULONG32` 型へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c2742-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="c2742-110">[出力] 例外レコードのコピーを受信するメモリ バッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c2742-110">[out] A pointer to a memory buffer that receives a copy of the exception record.</span></span> <span data-ttu-id="c2742-111">例外レコードとして返されます、 [MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception)型。</span><span class="sxs-lookup"><span data-stu-id="c2742-111">The exception record is returned as a [MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2742-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="c2742-112">Return Value</span></span>  
 <span data-ttu-id="c2742-113">戻り値は、成功の場合は `S_OK` で、失敗の場合は `HRESULT` コードです。</span><span class="sxs-lookup"><span data-stu-id="c2742-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="c2742-114">次が `HRESULT` コードに含まれることはありますが、限定されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c2742-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="c2742-115">リターン コード</span><span class="sxs-lookup"><span data-stu-id="c2742-115">Return code</span></span>|<span data-ttu-id="c2742-116">説明</span><span class="sxs-lookup"><span data-stu-id="c2742-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="c2742-117">メソッドが成功しました。</span><span class="sxs-lookup"><span data-stu-id="c2742-117">Method succeeded.</span></span> <span data-ttu-id="c2742-118">例外レコードは出力バッファーにコピーされました。</span><span class="sxs-lookup"><span data-stu-id="c2742-118">The exception record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="c2742-119">例外レコードはターゲットに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="c2742-119">No exception record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="c2742-120">入力バッファーのサイズは `sizeof(MINIDUMP_EXCEPTION)` と等しくありません。</span><span class="sxs-lookup"><span data-stu-id="c2742-120">The input buffer size is not equal to `sizeof(MINIDUMP_EXCEPTION)`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2742-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="c2742-121">Remarks</span></span>  
 <span data-ttu-id="c2742-122">[MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception) dbghelp.h および imagehlp.h Windows SDK で定義された構造です。</span><span class="sxs-lookup"><span data-stu-id="c2742-122">[MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception) is a structure defined in dbghelp.h and imagehlp.h in the Windows SDK.</span></span>  
  
 <span data-ttu-id="c2742-123">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="c2742-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2742-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="c2742-124">Requirements</span></span>  
 <span data-ttu-id="c2742-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2742-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2742-126">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="c2742-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c2742-127">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2742-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2742-128">**.NET Framework のバージョン:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c2742-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2742-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2742-129">See also</span></span>
- [<span data-ttu-id="c2742-130">ICLRDataTarget3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2742-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [<span data-ttu-id="c2742-131">GetExceptionContextRecord メソッド</span><span class="sxs-lookup"><span data-stu-id="c2742-131">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="c2742-132">GetExceptionThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="c2742-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
