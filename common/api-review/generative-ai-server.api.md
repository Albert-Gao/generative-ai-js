## API Report File for "@google/generative-ai"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

// @public
export interface CachedContent extends CachedContentBase {
    // (undocumented)
    createTime?: string;
    // (undocumented)
    name?: string;
    // (undocumented)
    ttl?: string;
    // (undocumented)
    updateTime?: string;
}

// @public (undocumented)
export interface CachedContentBase {
    // (undocumented)
    contents: Content[];
    // (undocumented)
    model?: string;
    // (undocumented)
    systemInstruction?: string | Part | Content;
    // (undocumented)
    toolConfig?: ToolConfig;
    // (undocumented)
    tools?: Tool[];
}

// @public
export interface CachedContentCreateParams extends CachedContentBase {
    // (undocumented)
    ttlSeconds?: number;
}

// @public
export interface CachedContentUpdateParams {
    // (undocumented)
    cachedContent: CachedContentCreateParams;
    updateMask: string[];
}

// @public
export interface Content {
    // (undocumented)
    parts: Part[];
    // (undocumented)
    role: string;
}

// @public
export interface ErrorDetails {
    // (undocumented)
    "@type"?: string;
    // (undocumented)
    [key: string]: unknown;
    // (undocumented)
    domain?: string;
    // (undocumented)
    metadata?: Record<string, unknown>;
    // (undocumented)
    reason?: string;
}

// @public
export interface FileData {
    // (undocumented)
    fileUri: string;
    // (undocumented)
    mimeType: string;
}

// @public
export interface FileDataPart {
    // (undocumented)
    fileData: FileData;
    // (undocumented)
    functionCall?: never;
    // (undocumented)
    functionResponse?: never;
    // (undocumented)
    inlineData?: never;
    // (undocumented)
    text?: never;
}

// @public
export interface FileMetadata {
    // (undocumented)
    displayName?: string;
    // (undocumented)
    mimeType: string;
    // (undocumented)
    name?: string;
}

// @public
export interface FileMetadataResponse {
    // (undocumented)
    createTime: string;
    // (undocumented)
    displayName?: string;
    error?: RpcStatus;
    // (undocumented)
    expirationTime: string;
    // (undocumented)
    mimeType: string;
    // (undocumented)
    name: string;
    // (undocumented)
    sha256Hash: string;
    // (undocumented)
    sizeBytes: string;
    // (undocumented)
    state: FileState;
    // (undocumented)
    updateTime: string;
    // (undocumented)
    uri: string;
    videoMetadata?: VideoMetadata;
}

// @public
export enum FileState {
    // (undocumented)
    ACTIVE = "ACTIVE",
    // (undocumented)
    FAILED = "FAILED",
    // (undocumented)
    PROCESSING = "PROCESSING",
    // (undocumented)
    STATE_UNSPECIFIED = "STATE_UNSPECIFIED"
}

// @public
export interface FunctionCall {
    // (undocumented)
    args: object;
    // (undocumented)
    name: string;
}

// @public (undocumented)
export interface FunctionCallingConfig {
    // (undocumented)
    allowedFunctionNames?: string[];
    // Warning: (ae-forgotten-export) The symbol "FunctionCallingMode" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    mode?: FunctionCallingMode;
}

// @public
export interface FunctionCallPart {
    // (undocumented)
    fileData?: never;
    // (undocumented)
    functionCall: FunctionCall;
    // (undocumented)
    functionResponse?: never;
    // (undocumented)
    inlineData?: never;
    // (undocumented)
    text?: never;
}

// @public
export interface FunctionDeclaration {
    description?: string;
    name: string;
    parameters?: FunctionDeclarationSchema;
}

// @public
export interface FunctionDeclarationSchema {
    description?: string;
    properties: {
        [k: string]: FunctionDeclarationSchemaProperty;
    };
    required?: string[];
    type: FunctionDeclarationSchemaType;
}

// @public
export interface FunctionDeclarationSchemaProperty extends Schema {
}

// @public
export enum FunctionDeclarationSchemaType {
    ARRAY = "ARRAY",
    BOOLEAN = "BOOLEAN",
    INTEGER = "INTEGER",
    NUMBER = "NUMBER",
    OBJECT = "OBJECT",
    STRING = "STRING"
}

// @public
export interface FunctionDeclarationsTool {
    functionDeclarations?: FunctionDeclaration[];
}

// @public
export interface FunctionResponse {
    // (undocumented)
    name: string;
    // (undocumented)
    response: object;
}

// @public
export interface FunctionResponsePart {
    // (undocumented)
    fileData?: never;
    // (undocumented)
    functionCall?: never;
    // (undocumented)
    functionResponse: FunctionResponse;
    // (undocumented)
    inlineData?: never;
    // (undocumented)
    text?: never;
}

// @public
export interface GenerativeContentBlob {
    data: string;
    // (undocumented)
    mimeType: string;
}

// @public
export class GoogleAICacheManager {
    constructor(apiKey: string, _requestOptions: RequestOptions);
    // (undocumented)
    apiKey: string;
    create(createOptions: CachedContentCreateParams): Promise<CachedContent>;
    delete(name: string): Promise<void>;
    get(name: string): Promise<CachedContent>;
    list(listParams?: ListParams): Promise<ListCacheResponse>;
    // (undocumented)
    model: string;
    // (undocumented)
    systemInstruction?: string | Part | Content;
    // (undocumented)
    toolConfig?: ToolConfig;
    // (undocumented)
    tools?: Tool[];
    // (undocumented)
    ttl?: string;
    update(name: string, updateParams: CachedContentUpdateParams): Promise<CachedContent>;
}

// @public
export class GoogleAIFileManager {
    constructor(apiKey: string, _requestOptions?: RequestOptions);
    // (undocumented)
    apiKey: string;
    deleteFile(fileId: string): Promise<void>;
    getFile(fileId: string): Promise<FileMetadataResponse>;
    listFiles(listParams?: ListParams): Promise<ListFilesResponse>;
    uploadFile(filePath: string, fileMetadata: FileMetadata): Promise<UploadFileResponse>;
}

// @public
export interface InlineDataPart {
    // (undocumented)
    fileData?: never;
    // (undocumented)
    functionCall?: never;
    // (undocumented)
    functionResponse?: never;
    // (undocumented)
    inlineData: GenerativeContentBlob;
    // (undocumented)
    text?: never;
}

// @public (undocumented)
export interface ListCacheResponse {
    // (undocumented)
    cachedContents: CachedContent[];
    // (undocumented)
    nextPageToken?: string;
}

// @public
export interface ListFilesResponse {
    // (undocumented)
    files: FileMetadataResponse[];
    // (undocumented)
    nextPageToken?: string;
}

// @public
export interface ListParams {
    // (undocumented)
    pageSize?: number;
    // (undocumented)
    pageToken?: string;
}

// @public
export type Part = TextPart | InlineDataPart | FunctionCallPart | FunctionResponsePart | FileDataPart;

// @public
export interface RequestOptions {
    apiClient?: string;
    apiVersion?: string;
    baseUrl?: string;
    customHeaders?: Headers | Record<string, string>;
    timeout?: number;
}

// @public
export interface ResponseSchema extends Schema {
}

// @public
export interface RpcStatus {
    code: number;
    details?: ErrorDetails[];
    message: string;
}

// @public
export interface Schema {
    description?: string;
    enum?: string[];
    example?: unknown;
    format?: string;
    items?: FunctionDeclarationSchema;
    nullable?: boolean;
    properties?: {
        [k: string]: FunctionDeclarationSchema;
    };
    required?: string[];
    type?: FunctionDeclarationSchemaType;
}

// @public
export interface TextPart {
    // (undocumented)
    fileData?: never;
    // (undocumented)
    functionCall?: never;
    // (undocumented)
    functionResponse?: never;
    // (undocumented)
    inlineData?: never;
    // (undocumented)
    text: string;
}

// @public
export type Tool = FunctionDeclarationsTool;

// @public
export interface ToolConfig {
    // (undocumented)
    functionCallingConfig: FunctionCallingConfig;
}

// @public
export interface UploadFileResponse {
    // (undocumented)
    file: FileMetadataResponse;
}

// @public
export interface VideoMetadata {
    videoDuration: string;
}

// (No @packageDocumentation comment for this package)

```