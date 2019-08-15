---
title: ICLRDataTarget3::GetExceptionContextRecord メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetContextRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07065b15f449c2bcb84df7bbdcce65d61de007ee
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038331"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a><span data-ttu-id="a161b-102">ICLRDataTarget3::GetExceptionContextRecord メソッド</span><span class="sxs-lookup"><span data-stu-id="a161b-102">ICLRDataTarget3::GetExceptionContextRecord Method</span></span>
<span data-ttu-id="a161b-103">ターゲット プロセスに関連付けられたコンテキスト レコードを取得するために、共通言語ランタイム (CLR: Common Language Runtime) データ アクセス サービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a161b-103">Called by the common language runtime (CLR) data access services to retrieve the context record associated with the target process.</span></span> <span data-ttu-id="a161b-104">たとえば、ダンプターゲットの場合、これは Windows デバッグヘルプライブラリ (dbghelp) の[MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump)関数`ExceptionParam`の引数を使用して渡されたコンテキストレコードと同じになります。</span><span class="sxs-lookup"><span data-stu-id="a161b-104">For example, for a dump target, this would be equivalent to the context record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a161b-105">構文</span><span class="sxs-lookup"><span data-stu-id="a161b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a161b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a161b-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="a161b-107">[入力] 入力バッファー サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="a161b-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="a161b-108">これはコンテキスト レコードを格納するのに十分な大きさである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a161b-108">This must be large enough to accommodate the context record.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="a161b-109">[出力] 実際にバッファーに書き込まれるバイト数を受け取る `ULONG32` 型へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a161b-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="a161b-110">[出力] コンテキスト レコードのコピーを受け取るメモリ バッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a161b-110">[out] A pointer to a memory buffer that receives a copy of the context record.</span></span> <span data-ttu-id="a161b-111">例外レコードは、[コンテキスト](/windows/win32/api/winnt/ns-winnt-arm64_nt_context)型として返されます。</span><span class="sxs-lookup"><span data-stu-id="a161b-111">The exception record is returned as a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a161b-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="a161b-112">Return Value</span></span>  
 <span data-ttu-id="a161b-113">戻り値は、成功の場合は `S_OK` で、失敗の場合は `HRESULT` コードです。</span><span class="sxs-lookup"><span data-stu-id="a161b-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="a161b-114">次が `HRESULT` コードに含まれることはありますが、限定されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a161b-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="a161b-115">リターン コード</span><span class="sxs-lookup"><span data-stu-id="a161b-115">Return code</span></span>|<span data-ttu-id="a161b-116">説明</span><span class="sxs-lookup"><span data-stu-id="a161b-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="a161b-117">メソッドが成功しました。</span><span class="sxs-lookup"><span data-stu-id="a161b-117">Method succeeded.</span></span> <span data-ttu-id="a161b-118">コンテキスト レコードは出力バッファーにコピーされました。</span><span class="sxs-lookup"><span data-stu-id="a161b-118">The context record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="a161b-119">コンテキスト レコードはターゲットに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="a161b-119">No context record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="a161b-120">入力バッファーのサイズが足りないため、コンテキスト レコードを格納できません。</span><span class="sxs-lookup"><span data-stu-id="a161b-120">The input buffer size is not large enough to accommodate the context record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a161b-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="a161b-121">Remarks</span></span>  
 <span data-ttu-id="a161b-122">[CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context)は、Windows SDK によって提供されるヘッダーで定義されているプラットフォーム固有の構造体です。</span><span class="sxs-lookup"><span data-stu-id="a161b-122">[CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) is a platform-specific structure defined in headers provided by the Windows SDK.</span></span>  
  
 <span data-ttu-id="a161b-123">このメソッドは、デバッグ アプリケーションの作成者によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="a161b-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a161b-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="a161b-124">Requirements</span></span>  
 <span data-ttu-id="a161b-125">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a161b-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a161b-126">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="a161b-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="a161b-127">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="a161b-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a161b-128">**.NET Framework のバージョン:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a161b-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a161b-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="a161b-129">See also</span></span>

- [<span data-ttu-id="a161b-130">ICLRDataTarget3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a161b-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [<span data-ttu-id="a161b-131">GetExceptionRecord メソッド</span><span class="sxs-lookup"><span data-stu-id="a161b-131">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
- [<span data-ttu-id="a161b-132">GetExceptionThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="a161b-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
